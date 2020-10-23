<div id="wrapper">
<h1 id="sorting">Sorting</h1>
<h4 id="description">Description</h4>
<p>A simple as it gets. Sort the input we provide you.</p>
<h4 id="endpoint">Endpoint</h4>
<p>Provide a <code>POST</code> endpoint <code>/sort</code> that given a list of numbers will return the sorted list.
For evaluation we will hit your endpoint once for every test case.</p>
<h4 id="input">Input</h4>
<p>The <code>HTTP POST</code> request will come with a body of <code>Content-Type: application/json</code> containing a list of length <strong>n</strong> of numbers <strong>i</strong>.</p>
<h4 id="output">Output</h4>
<p>The expected <code>HTTP</code> response will come with a body of <code>Content-Type: application/json</code> containing the sorted input list.</p>
<h4 id="limits">Limits</h4>
<ul>
<li>1 ≤ <strong>n</strong> ≤ 10<sup>7</sup></li>
<li>-10<sup>4</sup>≤ <strong>i</strong> ≤ 10<sup>4</sup>  </li>
<li>HTTP request timeout: 5s<br>(Note that certain frameworks tend to be slow at at marshalling payloads, so choose them wisely.)</li>
</ul>
<h4 id="sample">Sample</h4>
<pre><code>Input
[1, 42, 3, 8]
Output
[1, 3, 8, 42]
</code></pre>
</div>
