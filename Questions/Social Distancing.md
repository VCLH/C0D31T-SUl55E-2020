<div class="markdown-body"><h1 id="social-distancing">Social Distancing</h1>
<h3 id="instructions">Instructions</h3>
<p>The Singapore government has trouble deciding the limit for the number of people per train in the circuit breaker! Help them to resolve this conundrum by solving this question:</p>
<p><em>How many ways can <strong>X number of people</strong> sit in an MRT cabin with <strong>Y number of seats</strong> given that there is a <strong>required safety distance of Z seats</strong>?</em></p>
<p>Note: The order of the people do not matter.</p>
<p>Expose a <code>POST</code> endpoint <code>/social_distancing</code> for us to verify!</p>
<h4 id="input">Input</h4>
<pre><code class="language-json">{
    "tests": {
        "0": {
            "seats": 8,
            "people": 3,
            "spaces": 1
        },
        "1": {
            "seats": 7,
            "people": 3,
            "spaces": 1
        },
        "2": {
            "seats": 6,
            "people": 2,
            "spaces": 2
        },
        ...
    }
}</code></pre>
<h4 id="output-expected">Output Expected</h4>
<pre><code class="language-json5">{
    "answers": {
        "0": 20,
        "1": 10,
        "2": 6,
        ...
    }
}</code></pre>
<h3 id="example">Example</h3>
<pre><code>Given that seats <span class="token operator">=</span> <span class="token number">6</span><span class="token punctuation">,</span> people <span class="token operator">=</span> <span class="token number">3</span><span class="token punctuation">,</span> spaces <span class="token operator">=</span> <span class="token number">1</span>
Expected Answer<span class="token operator">:</span> <span class="token number">4</span></code></pre><h3 id="explanation">Explanation</h3>
<p>S denotes an empty seat and P denotes a person sitting on a seat</p>
<p>Note: The order of the people do not matter.</p>
<table>
<thead>
<tr>
<th align="center"><strong>Ways</strong></th>
<th align="center">S1</th>
<th align="center">S2</th>
<th align="center">S3</th>
<th align="center">S4</th>
<th align="center">S5</th>
<th align="center">S6</th>
</tr>
</thead>
<tbody><tr>
<td align="center">1</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
</tr>
<tr>
<td align="center">2</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
</tr>
<tr>
<td align="center">3</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
</tr>
<tr>
<td align="center">4</td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
<td align="center">S</td>
<td align="center"><strong>P</strong></td>
</tr>
</tbody></table>
<p>Actual number of test cases given may change.</p>
</div>
