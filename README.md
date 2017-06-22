# jose

[![Quicklisp dist](http://quickdocs.org/badge/jose.svg)](http://quickdocs.org/jose/)
[![Build Status](https://travis-ci.org/fukamachi/jose.svg?branch=master)](https://travis-ci.org/fukamachi/jose)
[![Coverage Status](https://coveralls.io/repos/fukamachi/jose/badge.svg?branch=master)](https://coveralls.io/r/fukamachi/jose)

A JSON Object Signing and Encryption (JOSE) implementation for Common Lisp.

## Usage

```common-lisp
(defvar *key* (ironclad:ascii-string-to-byte-array "my$ecret"))

(jose:encode :hs256 *key* '(("hello" . "world")))
;=> "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJoZWxsbyI6IndvcmxkIn0.Vr0VKL9WHX9lUPWzrE0DX4fEvl0_CgnKlzI2mWiro8E"

(jose:decode :hs256 *key* *)
;=> (("hello" . "world"))
```

## Supported Algorithms

* HS256
* HS384
* HS512
* RS256
* RS384
* RS512
* none

## Author

* Eitaro Fukamachi (e.arrows@gmail.com)

## Copyright

Copyright (c) 2017 Eitaro Fukamachi (e.arrows@gmail.com)

## License

Licensed under the BSD 2-Clause License.
