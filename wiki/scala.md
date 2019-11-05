# Scala

- Run futures one after another: use `.map`

/!\ Make sure to check return types. For instance if something returns a `Future[Future[T]]` using `.map` will only wait for the outer future to be completed. In this case `.flatMap` will produce the desired behaviour.

- Webapp/Rest Api example: [https://github.com/ghelouis/scala-play-example](https://github.com/ghelouis/scala-play-example)

## SBT

- Run scala repl with access to a project's dependencies: `sbt console`

Best to run following commands from within `sbt` (don't start the jvm
everytime):
- Run specific test class: `testOnly *UserSpec`
