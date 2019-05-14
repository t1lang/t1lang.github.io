# T1

T1 is a programming language which aims at providing better support for
constrained environments, especially embedded systems with very little
RAM. It should provide the following features:

  - Embeddable within C-based application with no OS dependency ("bare
    metal" systems).

  - Lightweight coroutines with strong guarantees on maximum stack usage.

  - Type-safe and memory-safe by default.

  - Predictable memory layout for easier integration with hardware.

  - Portable output (T1 code may be compiled to plain C).

  - Very small code footprint through generation of token-threaded code.

  - Generic metaprogramming support.

  - Flexible object-oriented support.

T1 can be viewed as an evolution of the T0 programming language, a
custom Forth-like language integrated in
[BearSSL](https://www.bearssl.org/), an SSL/TLS library specialized for
embedded systems. T0 offers lightweight coroutines, a token-threaded
code output, and strong guarantees on maximum stack growth. T1 adds a
rich type system, a compile-time static analysis phase, memory safety,
optional dynamic memory allocation (with a garbage collector), and other
features that make it more a general-purpose language (e.g. namespaces).

The [T1 specification](t1spec.pdf) describes the language and contains
explanations about its design choices, some of which being uncommon or
even seemingly outrageous (e.g. lack of support for recursion, whole
program deductive type analysis, postfix syntax...).

# License

Everything here is provided under the [MIT license](LICENSE.html). This
means that you can use as you wish; you don't have to credit me; if it
breaks anything, it's your fault, not mine.

# Status

T1 is a work-in-progress. Current status is the following:

  - The [specification](t1spec.pdf) is mostly stable.

  - The standard library is inexistent at this point, except for very
    basic features (e.g. operations on integer types). It should be
    enhanced with, at least, some container types beyond simple arrays
    (e.g. growable vectors, sorted maps...) and documented.

  - A [bootstrap interpreter/compiler](https://github.com/t1lang/t1bootstrap)
    is being written in C#. Its role is, ultimately, to compile the
    "real" T1 compiler, which will be written in T1 and then compile
    itself (as per immemorial tradition for programming language
    design). Interpreter, type analysis, and parts of the output
    generator have been implemented so far.
