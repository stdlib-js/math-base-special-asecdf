<!--

@license Apache-2.0

Copyright (c) 2024 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# asecdf

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Compute the [arcsecant][arcsecant] (in degrees) of a single-precision floating-point number.

<section class="installation">

## Installation

```bash
npm install @stdlib/math-base-special-asecdf
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var asecdf = require( '@stdlib/math-base-special-asecdf' );
```

#### asecdf( x )

Computes the [arcsecant][arcsecant] (in degrees) of a single-precision floating-point number.

```javascript
var sqrtf = require( '@stdlib/math-base-special-sqrtf' );

var v = asecdf( Infinity );
// returns 90.0

v = asecdf( 2.0 * sqrtf( 3.0 ) / 3.0 );
// returns ~30.0

v = asecdf( sqrtf( 2.0 ) );
// returns 45.0

v = asecdf( 2.0 );
// returns ~60.0

v = asecdf( 1.0 );
// returns 0.0

v = asecdf( NaN );
// returns NaN
```

The domain of `x` is restricted to the intervals `[-inf, -1]` and `[1, inf]`. For `x` outside of these intervals, the function returns `NaN`.

```javascript
var v = asecdf( -0.5 );
// returns NaN

v = asecdf( 0.5 );
// returns NaN
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var uniform = require( '@stdlib/random-array-uniform' );
var logEachMap = require( '@stdlib/console-log-each-map' );
var asecdf = require( '@stdlib/math-base-special-asecdf' );

var x = uniform( 100, 1.1, 5.1, {
    'dtype': 'float32'
});

logEachMap( 'asecdf(%0.4f) = %0.4f', x, asecdf );
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/math/base/special/asecdf.h"
```

#### stdlib_base_asecdf( x )

Computes the [arcsecant][arcsecant] (in degrees) of a single-precision floating-point number.

```c
float out = stdlib_base_asecdf( 1.0f );
// returns 0.0f

out = stdlib_base_asecdf( 2.0f );
// returns ~60.0f
```

The function accepts the following arguments:

-   **x**: `[in] float` input value.

```c
float stdlib_base_asecdf( const float x );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/math/base/special/asecdf.h"
#include <stdio.h>

int main( void ) {
    const float x[] = { 1.1f, 1.55f, 1.99f, 2.44f, 2.88f, 3.32f, 3.77f, 4.21f, 4.66f, 5.1f };

    float v;
    int i;
    for ( i = 0; i < 10; i++ ) {
        v = stdlib_base_asecdf( x[ i ] );
        printf( "acscd(%f) = %f\n", x[ i ], v );
    }
}
```

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/math-base/special/asec`][@stdlib/math/base/special/asec]</span><span class="delimiter">: </span><span class="description">compute the inverse (arc) secant of a number.</span>
-   <span class="package-name">[`@stdlib/math-base/special/asech`][@stdlib/math/base/special/asech]</span><span class="delimiter">: </span><span class="description">compute the hyperbolic arcsecant of a number.</span>
-   <span class="package-name">[`@stdlib/math-base/special/acosdf`][@stdlib/math/base/special/acosdf]</span><span class="delimiter">: </span><span class="description">compute the arccosine (in degrees) of a single-precision floating-point number.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/math-base-special-asecdf.svg
[npm-url]: https://npmjs.org/package/@stdlib/math-base-special-asecdf

[test-image]: https://github.com/stdlib-js/math-base-special-asecdf/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/math-base-special-asecdf/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/math-base-special-asecdf/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/math-base-special-asecdf?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/math-base-special-asecdf.svg
[dependencies-url]: https://david-dm.org/stdlib-js/math-base-special-asecdf/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/math-base-special-asecdf/tree/deno
[deno-readme]: https://github.com/stdlib-js/math-base-special-asecdf/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/math-base-special-asecdf/tree/umd
[umd-readme]: https://github.com/stdlib-js/math-base-special-asecdf/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/math-base-special-asecdf/tree/esm
[esm-readme]: https://github.com/stdlib-js/math-base-special-asecdf/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/math-base-special-asecdf/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/math-base-special-asecdf/main/LICENSE

[arcsecant]: https://en.wikipedia.org/wiki/Inverse_trigonometric_functions

<!-- <related-links> -->

[@stdlib/math/base/special/asec]: https://github.com/stdlib-js/math-base-special-asec

[@stdlib/math/base/special/asech]: https://github.com/stdlib-js/math-base-special-asech

[@stdlib/math/base/special/acosdf]: https://github.com/stdlib-js/math-base-special-acosdf

<!-- </related-links> -->

</section>

<!-- /.links -->
