<div class="markdown-body"><h1 id="supermarket-maze">Supermarket Maze</h1>
<h3 id="instructions">Instructions</h3>
<p>While shopping for groceries you find that the supermarket is like a maze filled with blocked walkways that hinder your shopping sprees. </p>
<p>Given the floor plan of the supermarket, find the number of steps made within the shortest path from the entrance to the checkout counter.</p>
<p>To make things interesting some mazes are unsolvable, in that case return -1 as number of steps to solve the maze! </p>
<p>Expose a <code>POST</code> endpoint <code>/supermarket</code> for us to verify!</p>
<h4 id="input">Input</h4>
<pre><code class="language-json5">{
    "tests": {
        "0":{
            "maze": [[1, 1, 1, 0, 1, 1, 1, 1, 1, 1, 1],
                     [1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1],
                     [1, 1, 1, 1, 1, 0, 1, 1, 1, 0, 1],
                     [1, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1],
                     [1, 0, 1, 0, 1, 1, 1, 1, 1, 0, 1],
                     [1, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1],
                     [1, 0, 1, 1, 1, 1, 1, 1, 1, 0, 1],
                     [1, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1],
                     [1, 0, 1, 0, 1, 1, 1, 1, 1, 0, 1],
                     [1, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1],
                     [1, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1]],
            "start": [3, 0],
            "end": [1, 10]
        },
        "1": {
            "maze": [[1, 1, 1, 0, 1, 1, 1, 1, 1],
                     [1, 1, 1, 0, 0, 0, 0, 0, 1],
                     [1, 1, 1, 0, 1, 1, 1, 0, 1],
                     [1, 1, 1, 0, 0, 0, 1, 0, 1],
                     [1, 1, 1, 1, 1, 0, 1, 0, 1],
                     [1, 0, 0, 0, 1, 0, 1, 0, 1],
                     [1, 0, 1, 1, 1, 0, 1, 0, 1],
                     [1, 0, 0, 0, 0, 0, 1, 0, 1],
                     [1, 1, 1, 1, 1, 1, 1, 0, 1]],
            "start": [3, 0],
            "end": [7, 8]
        },
        "2": {
          "maze": [[1, 1, 1, 0, 1, 1, 1, 1, 1],
                   [1, 1, 1, 0, 0, 0, 0, 0, 1],
                   [1, 1, 1, 0, 1, 1, 1, 0, 1],
                   [1, 1, 1, 0, 0, 0, 1, 0, 1],
                   [1, 1, 1, 1, 1, 0, 1, 1, 1],
                   [1, 0, 0, 0, 1, 0, 1, 0, 1],
                   [1, 0, 1, 1, 1, 0, 1, 0, 1],
                   [1, 0, 0, 0, 0, 0, 1, 0, 1],
                   [1, 1, 1, 1, 1, 1, 1, 0, 1]],
          "start": [3, 0],
          "end": [7, 8]
        },
        ...
    }
}</code></pre>
<h4 id="output-expected">Output Expected</h4>
<pre><code class="language-json5">{
    "answers": {
            "0": 29,
            "1": 13,
            "2": -1,
            ...
    }
}</code></pre>
<h3 id="limitations">Limitations</h3>
<ol>
<li>Assume that the start point is <code>(X,0)</code> where <code>X can be the x-coordinate within the length of the maze</code></li>
<li>No diagonal movement</li>
<li>The floor plan<ul>
<li>A wall is represented by <code>1</code></li>
<li>A walkable space is represented by <code>0</code></li>
</ul>
</li>
</ol>
<h3 id="example">Example</h3>
<h4 id="example-input">Example Input</h4>
<pre><code><span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">]</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">]</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">]</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">]</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">]</span>
<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">]</span>

Coordinates will be given <span class="token keyword">in</span> <span class="token keyword">as</span> <span class="token punctuation">[</span>x<span class="token operator">-</span>axis<span class="token punctuation">,</span> y<span class="token operator">-</span>axis<span class="token punctuation">]</span>

start<span class="token operator">:</span> <span class="token punctuation">[</span><span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">0</span><span class="token punctuation">]</span>
end<span class="token operator">:</span> <span class="token punctuation">[</span><span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">]</span></code></pre><h4 id="example-output">Example Output</h4>

<pre><code>answer<span class="token operator">:</span> <span class="token number">9</span></code></pre><h5 id="visualization">Visualization</h5>
<p>[1, 1, 1, <b style="color:red">0</b>, 1, 1, 1]<br>
[1, 0, 1, <b style="color:red">0</b>, 0, 0, 1]<br>
[1, 0, <b style="color:red">0</b>, <b style="color:red">0</b>, 1, 0, 1]<br>
[1, 1, <b style="color:red">0</b>, 1, 1, 1, 1]<br>
[1, 0, <b style="color:red">0</b>, <b style="color:red">0</b>, <b style="color:red">0</b>, 1, 1]<br>
[1, 1, 1, 1, <b style="color:red">0</b>, 1, 1]</p>
<p>Actual number of test cases given may change.</p>
</div>
