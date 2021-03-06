<body>
<h1>Cluster</h1>
<p>Given an area (2D array of '1's, '0s' and '*'s) at a specific time snapshot, you are tasked to find the number of clusters.</p>
<p>'1' represents an infected individual who has the ability to transmit the virus.</p>
<p>'0' represents an uninfected individual who can be infected by an infected person . If infected, this individual has the ability of an infected individual, and transmit the virus.</p>
<p>'*' represents a space where there are no individuals.</p>
<p>The virus can be transmitted horizontally, vertically and diagonally by a distance of 1 in the area.</p>
<p>A cluster is formed if there are infected individuals, or if there are virus transmissions between infected individuals and non-infected individuals.</p>
<p>You can assume the area is always made up by a constant length and breadth and can disregard anything beyond the given area. Individuals are also static and cannot move.</p>

<h2>Constraints</h2>
<p>3 &lt;= length of area &lt;= 1000</p>
<p>3 &lt;= breadth of area &lt;= 1000</p>

<h2>Sample Input 1</h2>
<pre><code class="language-json">
  [
    ["*", "*", "*", "*"],
    ["*", "1", "*", "*"],
    ["*", "*", "*", "*"],
    ["*", "*", "*", "1"],
    ["*", "*", "*", "*"]
  ]
</code></pre>

<h2>Sample Output 1</h2>
<pre><code class="language-json">{
  "answer": 2
}
</code></pre>

<h2>Sample Input 2</h2>
<pre><code class="language-json">
  [
    ["*", "*", "*", "*"],
    ["*", "1", "0", "*"],
    ["*", "*", "*", "*"],
    ["*", "*", "0", "0"],
    ["*", "*", "*", "*"]
  ]
</code></pre>

<h2>Sample Output 2</h2>
<pre><code class="language-json">{
  "answer": 1
}
</code></pre>

<h2>Sample Input 3</h2>
<pre><code class="language-json">
  [
    ["*", "*", "*", "*"],
    ["*", "1", "0", "*"],
    ["*", "*", "*", "1"],
    ["*", "*", "0", "0"],
    ["*", "*", "*", "*"]
  ]
</code></pre>

<h2>Sample Output 3</h2>
<pre><code class="language-json">{
  "answer": 1
}
</code></pre>

<h2>Sample Input 4</h2>
<pre><code class="language-json">
  [
    ["1", "0", "*", "*"],
    ["0", "0", "*", "0"],
    ["*", "*", "0", "*"],
    ["*", "*", "*", "*"],
    ["*", "*", "*", "*"],
    ["*", "0", "0", "*"]
  ]
</code></pre>

<h2>Sample Output 4</h2>
<pre><code class="language-json">{
  "answer": 1
}
</code></pre>

<h2>Sample Input 5</h2>
<pre><code class="language-json">
  [
    ["*", "*", "*", "*", "*", "*", "*", "*", "*"],
    ["*", "0", "0", "0", "*", "*", "*", "*", "*"],
    ["*", "*", "1", "*", "*", "*", "*", "*", "*"],
    ["*", "0", "0", "0", "*", "*", "*", "*", "*"],
    ["*", "*", "*", "*", "0", "*", "*", "*", "*"],
    ["*", "*", "*", "*", "*", "0", "0", "*", "*"],
    ["*", "*", "*", "*", "1", "*", "*", "*", "0"],
    ["*", "*", "*", "*", "0", "*", "*", "0", "0"],
    ["*", "*", "*", "*", "*", "*", "*", "*", "*"],
    ["*", "*", "*", "*", "*", "*", "*", "*", "*"],
    ["*", "*", "*", "*", "*", "*", "*", "*", "*"],
    ["*", "*", "1", "0", "0", "*", "*", "*", "*"],
    ["*", "*", "*", "*", "*", "*", "*", "*", "*"]
  ]
</code></pre>

<h2>Sample Output 5</h2>
<pre><code class="language-json">{
  "answer": 2
}
</code></pre>

<h2>Evaluation</h2>
<p>Your solution will be run against multiple random test cases. Be sure to include corner cases.</p>
<h2>Requirements</h2>
<p>Expose 1 POST endpoint /cluster for evaluation</p>

</body>
