<body>
    <h2>Revisit Geometry</h2>
<p>You are given coordinates of a shape and straight line. Your task is to find out all the possible points of intersection.</p>
<h3>Requirements</h3>
<ul>
<li>Expose a POST method with endpoint <code>/revisitgeometry</code></li>
<li>Return output result as json</li>
</ul>
<h3>Constraints</h3>
<ul>
<li>Input will be a JSON object of shape and line coordinates.</li>
<li>Join the coordinates in the same order of input.</li>
<li>Use straight lines to form the shape.</li>
<li>Input line will not overlap with any of the lines of the shape resulting in infite points of intersection.</li>
<li>n is an integer specifying the number of coordinates. 1 &lt;= n &lt;= 100.</li>
<li>The challenge is calibrated to a precision of .01</li>
</ul>
<h3>Input description</h3>
<p>Use straight line to join the co-ordinates and form the shape.<br>
Please join the coordinates in the same order of input and ensure that the last and first co-ordinate are joined by a line to complete the shape.<br>
<strong>Note:</strong> Shape must remain fixed, but you can extrapolate the straight line in any direction for infinite length to find the points of intersection. If the shape and straight line do not intersect, return an empty array [].<br>
The HTTP POST request will come with a body of Content-Type: application/json</p>
<h3>Scenario 1</h3>
<h4>Sample input JSON</h4>
<pre class="codehilite"><code class="language-json">{
  "shapeCoordinates": [
    { "x": 21, "y": 70 },
    { "x": 72, "y": 70 },
    { "x": 72, "y": 127 }
  ],
  "lineCoordinates": [
    { "x": -58, "y": 56 },
    { "x": -28, "y": 68 }
  ]
}</code></pre>

<h4>Sample output JSON</h4>
<pre class="codehilite"><code class="language-json">[
  { "x": 72, "y": 108 },
  { "x": 45.52, "y": 97.41 }
]</code></pre>

<hr>
<h3>Scenario 2</h3>
<h4>Sample input JSON</h4>
<pre class="codehilite"><code class="language-json">{
  "shapeCoordinates": [
    { "x": -21, "y": -18 },
    { "x": 71, "y": -18 },
    { "x": 71, "y": 71 },
    { "x": -21, "y": 71 }
  ],
  "lineCoordinates": [
    { "x": 68, "y": -8 },
    { "x": 108, "y": 42 }
  ]
}</code></pre>

<h4>Sample output JSON</h4>
<pre class="codehilite"><code class="language-json">[
  { "x": 60, "y": -18 },
  { "x": 71, "y": -4.25 }
]</code></pre>

<hr>
<h3>Scenario 3</h3>
<h4>Sample input JSON</h4>
<pre class="codehilite"><code class="language-json">{
      "shapeCoordinates":[
         {
            "x":63,
            "y":26
         },
         {
            "x":115,
            "y":26
         },
         {
            "x":115,
            "y":54
         },
         {
            "x":63,
            "y":54
         }
      ],
      "lineCoordinates":[
         {
            "x":-88,
            "y":85
         },
         {
            "x":-58,
            "y":97
         }
      ]
   }</code></pre>

<h4>Sample output JSON</h4>
<pre class="codehilite"><code class="language-json">[]</code></pre>
  
</body>
