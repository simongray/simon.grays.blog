---
date: 2020-03-01
location: Nørrebro, Copenhagen
---

Clojure: the Lisp that wants to spread
======================================
> NOTE: this blog post was originally published on my Github pages. At the time, it generated a lot of [discussion on Hacker News](https://news.ycombinator.com/item?id=22458827).

From its humble beginnings, Clojure was always meant to be a “hosted” language. It is important to note that while the Clojure of today is definitely a tightly integrated JVM (Java Virtual Machine) language, there were always multiple implementations of Clojure.

The language was consciously designed with its host abstracted away, apart from the host-specific functions in the java namespace and in glimpses of Java interop code. The same held for the [CLR implementation of Clojure](https://github.com/clojure/clojure-clr) for the .NET Common Language Runtime, released concurrently, with its very similar-looking interop code.

Interestingly, Rich Hickey made an implementation of Clojure in Common Lisp too, but abandoned it prior to the public announcement of Clojure.

Later, ClojureScript managed to do the same, but with a js namespace rather than a java one. The interop code also looks similar, though the js namespace is much more commonly referenced than any of the java ones, as everything in JavaScript derives from one big namespace (as opposed to discrete classes in discrete modules).

The decision to not try to entirely abstract the host away as some other languages do (Java for example, with respect to operating systems) has not in any way hindered the ability of different Clojure implementations to share code between them. At the same time, the different Clojure implementations retain the same level of access to the underlying machine that the languages whose runtimes they leech off (Java, C#, JavaScript) do.

That makes Clojure powerful.

Clojure is a well-designed language and, crucially, a newer language
with many of the past sins of older languages confidently thrown out (ubiquitous mutability, OOP and typing boilerplate) and great new things added in. It’s both a conservatively scoped and a fresh take on a programming language. That is great in itself, but to get from well-thought out to powerful, you need to multiply with something else: reach. Clojure is designed to reach beyond a single runtime, while being able to interoperate with its many implementations that constantly spread into different runtimes.

There’s always a little host-specific code in a host namespace. Always the ability to interoperate fully with the host code.

Nowadays, several different unofficial Clojure ports exist for other runtimes: [Clojerl](https://github.com/clojerl/clojerl) on BEAM (the Erlang virtual machine) or [Joker](https://github.com/candid82/joker) (written in Go). Common Lisp has also seen multiple attempts to get Clojure running: [clclojure](https://github.com/joinr/clclojure) and [cloture](https://github.com/ruricolist/cloture). Inspired-by languages include [Hy](https://github.com/hylang/hy) or [Pixie](https://github.com/pixie-lang/pixie) (for Python); or [Ferret](https://github.com/nakkaya/ferret) that compiles down to C++. Subsets of Clojure also exist in smaller invocations, such as several different implementations integrating Clojure with shell scripts. These are certainly interesting, but lie somewhat evenly spread on a spectrum of how fully-implemented they are.

Clojure CLR, I have a feeling, is mostly used to makes games using [Arcadia](https://github.com/arcadia-unity) (integration with the Unity game engine) and Arcadia is in fact creating its own competing Clojure compiler, [MAGIC](https://github.com/nasser/magic).
This is great for Clojure game development and less great for other things, but obviously reflects .NET reach more than it really does Clojure CLR as a language.

The big stars are still ClojureScript and Clojure on the JVM. ClojureScript has now spread beyond its initial borders into the confines of Node.js and a bunch of other JavaScript runtimes, but the biggest host platform is still by far the browser. And it’s excellent at that.

These days it’s common for Clojure libraries to either have a common Clojure implementation (facilitated with .cljc files) or alternative implementations of the library for both Clojure and ClojureScript. That’s a 2x multiplier you can apply just for the healthy library ecosystem that has been created for these two languages.

At the same time, the fact that Clojure’s primitives are easily serialisable led to using EDN (Extensible Data Notation) as the format of exchange between frontend and backend. This is similar to the relationship that JavaScript has with JSON. Since then, the [Transit](https://github.com/cognitect/transit-format) library has made that process even simpler by setting up a direct data pipe between ClojureScript and Clojure.

The way the languages are integrated today, Clojure developers doing full-stack development don’t really have to think about data serialisation/deserialisation. Writing code for frontend and backend differ mostly just in the way that the different implementations access the host platform. The functional aspects of Clojure, especially the immutability and focus on referential transparency, ensure that source code is mostly split into chunks of highly portable code, with the host-interop conveniently put aside in its own sections. You can move code between frontend and backend at your leisure.

So, the 2x multiplier awarded earlier for reach should really be incremented some more to reflect all of the code we don’t have to write – and more importantly: don’t have to think about. This is how the design of Clojure as a hosted language makes it more powerful.

Clojure’s main Achilles’ heel right now, with respect to reach, is its relatively slow application start-up time. This is the primary reason that Clojure hasn’t taken off as a language for Android development and for making desktop apps. This also makes Clojure slightly less suitable for command-line utilities, reducing its reach for writing these on the desktop OS platforms. And of course, Java never really took off as a language for developing desktop apps, other than GUIs made for in-house corporate software and research apps. And Minecraft.

That has not mattered as much as it might have, as the community has long been using ClojureScript for both [app development](https://cljsrn.org/) and writing shell scripts. Now we are able to leverage the [GraalVM Native Image](https://www.graalvm.org/latest/reference-manual/native-image/) compiler
too. By transpiling JVM bytecode into machine code, Clojure has inadvertently spread to yet another platform: native code.

And most recently, we have even been getting direct interop with Python from JVM Clojure using [libpython-clj](https://github.com/clj-python/libpython-clj) and interop with R through [clojisr](https://github.com/scicloj/clojisr).

This kind of reach of a single language is not as common among programming languages as you may think.

Clojure is (slowly) eating the world. Honestly, we should be thankful that the language continues to grow despite being fairly unorthodox, compared with the current norm of typed functional languages and the massive sea of object-oriented code that’s out there.  It’s also the odd child in the Lisp family with its functional, data-driven, and interop-heavy approach to programming.

And we can’t forget the terrible sin of putting starting parentheses in front of function names rather than after them!

Clojure is unorthodox. It exists in a world dominated by primarily object-oriented, imperative languages. But it is delivering lots of value already while constantly increasing its reach and benefiting from it in return.
