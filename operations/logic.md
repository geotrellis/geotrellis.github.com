---
layout: operations
title: Logic

tutorial: operations
num: 8
---

These sets of operation are relevant to all compound operations as they are used to load data, produce output formats, and as the functional programming constructs that are critical to operation composition.

#### Logic operations

Logical operations for composing compound operations. Scala package [geotrellis.logic.op.](http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.package)

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.AsList" targe="_blank">logic.AsList</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Return the result of the input operation as a List.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.Collect" targe="_blank">logic.Collect</a></code></td><td><div id="comment" class="fullcommenttop"><p>Takes a sequence of operations, and returns a Sequence of the results of those operations.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.CollectArray" targe="_blank">logic.CollectArray</a></code></td><td><div id="comment" class="fullcommenttop"><p>Takes a sequence of operations, and returns an Array of the results of those operations.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.Do$" targe="_blank">logic.Do</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Invoke a function that takes either one or two arguments.</p><p>Functionally speaking: Map an Op[A] into an Op[Z] using a function from A =&gt; Z or map an Op[A] and Op[B] into an Op[Z] using a function from (A,B) =&gt; Z.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.ForEach$" targe="_blank">logic.ForEach</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Evaluates the given operation (op) to get an array of A's. Then, applies the given function (f) to each item in the array in. The resulting array of Z's is returned.</p><p>Can also take two or three operations. See the documentation for <code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.ForEach2" targe="_blank">logic.ForEach2</a></code> and <code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.ForEach3" targe="_blank">logic.ForEach3</a></code> for usage.</p></div></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.If" targe="_blank">logic.If</a></code></td><td><div id="comment" class="fullcommenttop"><p>Conditionally executes one of two operations; if the Boolean Operation evaluates true, the first Operation executes, otherwise the second Operation executes.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.Reducer1" targe="_blank">logic.Reducer1</a></code></td><td><div id="comment" class="fullcommenttop"><p> Base class for operations that use a map and reduce step to allow for operations to be distributed over TiledRasterData.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.Reducer2" targe="_blank">logic.Reducer2</a></code></td><td><div id="comment" class="fullcommenttop"><p> * Base class for operations that take a raster operation and another operation, and use a map and reduce step to allow for operations to be distributed over TiledRasterData, and takes another operation.</p></div></td></tr>

<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.WithResult" targe="_blank">logic.WithResult</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>Run a function on the result of an operation</p><p>Functionally speaking, this represents the bind operation on the Operation monad.</p></div></div></td></tr>

</tbody>
</table>

For Haskell-inspired syntax, see [geotrellis.logic.applicative](http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.applicative.package) package.

<table class="bordered-table zebra-striped">
      <thead>
          <tr>
            <th>Operation</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.applicative.Apply" targe="_blank">logic.applicative.Apply</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "apply" (&lt;*&gt;) on Functor.</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.applicative.Fmap" targe="_blank">logic.applicative.Fmap</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "fmap" on Functor.
</p></div></div></td></tr>
<tr><td><code><a href="http://geotrellis.github.com/api.doc/latest/api/#geotrellis.logic.applicative.Pure" targe="_blank">logic.applicative.Pure</a></code></td><td><div id="comment" class="fullcommenttop"><div class="comment cmt"><p>This corresponds to Haskell's "pure" on Functor.
</p></div></div></td></tr>

</tbody>
</table>
