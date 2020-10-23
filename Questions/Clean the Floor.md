<div class="markdown-body"><h1 id="clean-the-floor">Clean the Floor</h1>
<h3 id="instructions">Instructions</h3>
<p>You find that cleaning the floor with the least amount of movement helps to calm your nerves. A value higher than 0 represents the dirtiness of the floor. Find out what is the least number of moves to clean the floor. </p>
<p>Expose a <code>POST</code> endpoint <code>/clean_floor</code> for us to verify!</p>
<h4 id="input">Input</h4>
<pre><code class="language-json5">{
  "tests": {
    "0": {
      "floor":[0, 1]
    },
    "1": {
      "floor":[1, 1]
    },
    ...
  }
}</code></pre>
<h4 id="output-expected">Output Expected</h4>
<pre><code class="language-json5">{
  "answers": {
    "0": 1,
    "1": 2,
    ...
  }
}</code></pre>
<h3 id="itty-bitty-details">Itty Bitty Details</h3>
<ol>
<li>The start point is always at position 0 of the array</li>
<li>Each move traverses 1 position in the array and performs 1 action</li>
<li>There are only 2 possible actions per move:<ul>
<li>If the position has <strong>dirt level &gt; 0</strong> then the dirt level decreases by 1 <em>(Spend some time and effort to clean the floor)</em></li>
<li>If the position has <strong>dirt level = 0</strong> then the dirt level increases by 1 <em>(You walked on a clean floor so you dirty it)</em></li>
</ul>
</li>
<li>When all values in the floor have a <strong>dirt level = 0</strong>, then the floor is clean!</li>
</ol>
<h3 id="examples">Examples</h3>
<h4 id="input-1">Input 1</h4>
<pre><code class="language-json5">[0, 1]</code></pre>
<h4 id="output-1">Output 1</h4>
<pre><code class="language-json5">1 Move to clean
Move 0: [0, 1]
Move 1: [0, 0] // You're done cleaning!</code></pre>
<h4 id="input-2">Input 2</h4>
<pre><code class="language-json5">[1, 1]</code></pre>
<h4 id="output-2">Output 2</h4>
<pre><code class="language-json5">2 Moves to clean
Move 0: [1, 1]
Move 1: [1, 0]
Move 2: [0, 0] // You're done cleaning!</code></pre>
<p>Actual number of test cases given may change.</p>
</div>
