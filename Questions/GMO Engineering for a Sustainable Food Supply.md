<div class="markdown-body"><h1 id="gmo-engineering-for-a-sustainable-food-supply">GMO Engineering for a Sustainable Food Supply</h1>
<p>The world is facing a food supply crisis!</p>
<p>In order to ensure sustainable and self-sufficient food supply, you are tasked to lead the national food council to increase the yield of crops by increasing its drought-resistance index (DRI) through genome sequencing.</p>
<p>A higher DRI would indicate higher survivability of the crop, increasing the yield of the crops.</p>
<p>A genome sequence is made up of exactly four alphabetical characters: A, C, G, T.</p>
<h2 id="task">Task</h2>
<p>Re-arrange the input sequences given in a way such that the DRI is maximized, to improve the crops' DRI.</p>
<p>To calculate the DRI of the crop, we will be calculating according to the following rules:</p>
<ol>
<li><p>A triple of A (AAA) will deduct the DRI by 10 points. So AAAAAA will reduce DRI by 20 points.</p>
</li>
<li><p>Every contiguous set of ACGT will increase the DRI by 15 points</p>
</li>
<li><p>A pair of CC will increase the DRI by 25 points.</p>
<p> So CCCC will increase DRI by 50 points.</p>
</li>
<li><p>Combination pairs of overlapping sequences will not be awarded double points i.e. AAACGT will not qualify for -10 (AAA) and +15 (ACGT)</p>
<p> Take note, in this case, AAA will be first used to qualify for -10 and it cannnot be used in the computation of ACGT. Thus, the score for AAACGT will be -10 instead of a total of +5 (-10 + 15)</p>
</li>
</ol>
<p>The score of DRI starts from 0, and can be negative/positive. Of course, the more positive the DRI score, the better the crop.</p>
<h2 id="examples">Examples</h2>
<p>Please note that the following examples are <strong>NOT</strong> optimal. They are meant to show DRI score calculations only.</p>
<h3 id="example-1">Example 1</h3>
<pre><code>Input<span class="token operator">:</span>  <span class="token constant">AAACCCAAAGGTTACTGAAAAG</span>
Output<span class="token operator">:</span> <span class="token constant">AAGAAGAAGAAGAATATTCCCC</span></code></pre><p>Explanation for example 1
This output will give us a DRI score of 50.</p>
<p>How is the DRI score tabluated:</p>
<ul>
<li>There is no occurence of AAA in the output, therefore, the DRI score is not deducted.</li>
<li>There is no ACGT in the output, therefore the DRI score is not increased.</li>
<li>There are 2 occurences of CC in the output, therefore, the DRI score is increased by 50 points.</li>
</ul>
<pre><code>Output <span class="token constant">DRI</span> Score <span class="token operator">:</span> <span class="token number">0</span> x <span class="token operator">-</span><span class="token number">20</span> <span class="token operator">+</span> <span class="token number">0</span> x <span class="token number">15</span> <span class="token operator">+</span> <span class="token number">2</span> x <span class="token number">25</span> <span class="token operator">=</span> <span class="token number">50</span></code></pre><h3 id="example-2">Example 2</h3>
<pre><code>Input<span class="token operator">:</span>  <span class="token constant">AAAAAACCTTTGGGGGGGTTTT</span>
Output<span class="token operator">:</span> <span class="token constant">AGAGAGAGAGAGCCTTTTTTTG</span></code></pre><p>Explanation for example 2
This output will give us a DRI score of 25.</p>
<p>How is the DRI score tabluated:</p>
<ul>
<li>There is no occurence of AAA in the output, therefore, the DRI score is not deducted.</li>
<li>There is no ACGT in the output, therefore the DRI score is not increased.</li>
<li>There is 1 occurence of CC in the output, therefore, the DRI score is increased by 25 points.</li>
</ul>
<pre><code>Output <span class="token constant">DRI</span> Score <span class="token operator">:</span> <span class="token number">0</span> x <span class="token operator">-</span><span class="token number">20</span> <span class="token operator">+</span> <span class="token number">0</span> x <span class="token number">15</span> <span class="token operator">+</span> <span class="token number">1</span> x <span class="token number">25</span> <span class="token operator">=</span> <span class="token number">25</span></code></pre><h2 id="api">API</h2>
<p>Please expose a <strong>POST</strong> endpoint /intelligent-farming for us to verify.</p>
<p>Additionally, please ensure that your response sets the HTTP header <strong>Content-Type</strong> to <strong>application/json</strong>. If this is not done, the evaluation call will fail.</p>
<h3 id="input-and-output-schema">Input and Output Schema</h3>
<p>The input and output JSON schemas are exactly the same. Simply put, mutate only the gene sequence content and return the same data structure.</p>
<ul>
<li><p>Do <strong>NOT</strong> change the values of the <em>runId</em> and the <em>id</em> shown in the schema below, doing so will result in submission failure.</p>
</li>
<li><p>Do <strong>NOT</strong> change the length of the <em>geneSequence</em>, doing so will result in submission failure.</p>
</li>
<li><p>Do <strong>NOT</strong> change the proportion of genes in the gene sequences, doing so will result in submission failure.</p>
<p>E.g. Input gene sequence = AAAA, and output gene sequence = ACGT</p>
</li>
<li><p>There will be exactly 10 gene sequences given to you. You must submit back 10 gene sequences, while not changing the value of <em>id</em> as mentioned in point 1. Any fewer or any more gene sequences returned will result in submission failure.</p>
</li>
</ul>
<pre><code><span class="token punctuation">{</span>
    <span class="token string">"runId"</span><span class="token operator">:</span> String <span class="token operator">&lt;</span><span class="token operator">-</span> Do <span class="token constant">NOT</span> Change
    <span class="token string">"list"</span><span class="token operator">:</span> <span class="token punctuation">[</span>
        <span class="token punctuation">{</span>
            <span class="token string">"id"</span><span class="token operator">:</span> Integer<span class="token punctuation">,</span> <span class="token operator">&lt;</span><span class="token operator">-</span> Do <span class="token constant">NOT</span> Change
            <span class="token string">"geneSequence"</span><span class="token operator">:</span> String <span class="token operator">&lt;</span><span class="token operator">-</span> Mutate <span class="token keyword">this</span>
        <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token operator">...</span>
    <span class="token punctuation">]</span>
<span class="token punctuation">}</span></code></pre><h3 id="sample-input-and-output">Sample Input and Output</h3>
<pre><code><span class="token punctuation">{</span>
    <span class="token string">"runId"</span><span class="token operator">:</span> <span class="token string">"a8098c1a-f86e-11da-bd1a-00112444be1e"</span>
    <span class="token string">"list"</span><span class="token operator">:</span><span class="token punctuation">[</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">1</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">6</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">7</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">8</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">9</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
        <span class="token punctuation">{</span> <span class="token string">"id"</span><span class="token operator">:</span> <span class="token number">10</span><span class="token punctuation">,</span> <span class="token string">"geneSequence"</span><span class="token operator">:</span> <span class="token string">"ACGT"</span> <span class="token punctuation">}</span>
    <span class="token punctuation">]</span>
<span class="token punctuation">}</span></code></pre><h2 id="contacts">Contacts</h2>
<ul>
<li>Tan Chee Wei</li>
<li>Jerald Gan</li>
<li>Louis Lim</li>
</ul>
<p><em>Don't forget to save the Earth!</em></p>
</div>
