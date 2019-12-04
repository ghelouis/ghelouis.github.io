# Scala

- Run futures one after another: use `.map`

/!\ Make sure to check return types. For instance if something returns a `Future[Future[T]]` using `.map` will only wait for the outer future to be completed. In this case `.flatMap` will produce the desired behaviour.

- Webapp/Rest Api example: [https://github.com/ghelouis/scala-play-example](https://github.com/ghelouis/scala-play-example)

## SBT

- Run scala repl with access to a project's dependencies: `sbt console`

To have a colored REPL put this into ~/.sbt/0.13/user.sbt:
```
initialize ~= { _ =>
  val ansi = System.getProperty("sbt.log.noformat", "false") != "true"
  if (ansi) System.setProperty("scala.color", "true")
}
```

Best to run following commands from within `sbt` (don't start the jvm
everytime):
- Run specific test class: `testOnly *UserSpec`

## Gotchas
Case classes are limited to 22 fields.

## Futures
Handle an exception thrown from within a future:

```scala
val futureResult = processStuf()
futureResult.map(result =>
  logger.info("all good").recover {
    case t: Throwable => logger.info("something went wrong :'(", t)
  }
```

## Tests

To test methods returning Futures, use [AsyncFlatSpec](http://www.scalatest.org/user_guide/async_testing)

```scala
// given
// ...

// when
val futureResult: Future[Int] = myService.myMethod()

// then
val futureResult.map(result => {
  assert(result == 42)
})
```

Note: with `AsyncFlatSpec` tests must return Future of assertions. If you only
want to test that some methods are called, i.e with mockito's `verify`, you can
add `succeed` as a last test (more or less equivalent to assert(1 == 1)):

```scala
// given
// ...

// when
val futureResult: Future[Int] = myService.myMethod()

// then
val futureResult.map(result => {
  verify(...)
  succeed
})
```
