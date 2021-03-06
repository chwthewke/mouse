# Mouse
Mouse is a small companion to the [Cats](https://github.com/typelevel/cats) functional programming library for Scala. It
includes convenient syntax (aka extension methods) found in [scalaz](https://github.com/scalaz/scalaz) that are considered out of scope for Cats proper.

The library arose from this [Cats issue](https://github.com/typelevel/cats/issues/791) and is a [Typelevel incubator](http://typelevel.org/projects/).

Mouse is published Scala 2.10.x and 2.11.x. For Scala.jvm:

`"com.github.benhutchison" %% "mouse" % "0.5"`
 
For scala.js:

`"com.github.benhutchison" %%% "mouse" % "0.5"`

[![Build Status](https://travis-ci.org/benhutchison/mouse.svg?branch=master)](https://travis-ci.org/benhutchison/mouse)

##Content

Mouse includes enrichments for:

- [Boolean](./shared/src/main/scala/mouse/boolean.scala)
- [Option](./shared/src/main/scala/mouse/option.scala)
- [String](./shared/src/main/scala/mouse/string.scala)

####Example:

```
scala> import mouse.all._
import mouse.all._

scala> true.option("Its true!")
res0: Option[String] = Some(Its true!)

scala> res0.cata(msg => s"Message received: ${msg}", "No message")
res1: String = Message received: Its true!

scala> "1.0".parseFloat
res0: cats.data.Xor[NumberFormatException,Float] = Right(1.0)

scala> "foo".parseIntValidated
res1: cats.data.Validated[NumberFormatException,Int] = Invalid(java.lang.NumberFormatException: For input string: "foo")
```

####Release Notes

Version `0.5` (Aug 16) is built against cats `0.7.0` but otherwise unchanged.

Version `0.4` (July 2016) includes a breaking package rename from `com.github.benhutchison.mouse` -> `mouse`. Rationale was
to follow cats and other modern libs convention of short, convenient package names. 

##Scope of Library

- Provide enrichments to classes from the Scala standard library that convert to Cats datatypes, 
or otherwise improve the functional programming experience.

- Make it easier to migrate source code between Scalaz and Cats.

##Contributing

Issues and pull requests are welcome. Code contributions should be aligned with the above scope to be included, and include unit tests.

This project supports the Typelevel [code of conduct](http://typelevel.org/conduct.html) and aims that its channels 
(mailing list, Gitter, github, etc.) to be welcoming environments for everyone.
 

