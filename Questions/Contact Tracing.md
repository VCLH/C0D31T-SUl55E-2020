<div class="markdown-body"><h1 id="contact-tracing">Contact Tracing</h1>
<p>A recent pandemic outbreak is spreading fast. C0D31T-SUl55E is one of the very few countries where the number of 
infected cases is only a handful. The administration of C0D31T-SUl55E wants to contain the spread of the 
outbreak within the country. As part of the containment plan, it wants to trace how each infected case in the country 
has contracted the infection.</p>
<p>A  Health Organisation says that the infected can be traced back to the origin by analysing the genome patterns 
of the infected against the available infected genome data set of the pandemic.</p>
<p>When the virus mutates and spreads, its genome code can be altered by one or two characters in its genome string of three 
character instructions. The minimal the alterations between the two genome strings, the more likely that they both are related.</p>
<p>Also, if the genome string has more than one instruction with instruction's first 
character altered, the mutation is said to be non-silent. In case of non-silent mutation, the virus exhibits change in its
effectiveness. </p>
<p>Can you write a program that could output the possible tracing paths of the infected and whether there 
is a non silent mutation of the virus in the trace?</p>
<h3 id="input-and-output">Input and Output</h3>
<h4 id="input">Input</h4>
<ul>
<li>You will be given a JSON string with Infected, Origin, and cluster of genomes information.<h4 id="output">Output</h4>
</li>
<li>You should return a String array of possible trace paths from Infected to Origin.<h3 id="rules-and-constraints">Rules and Constraints</h3>
</li>
<li>Expose a post endpoint "/contact_trace" that takes JSON input and returns a string array of trace paths.</li>
<li>Your output should contain all possible trace paths.</li>
<li>All genome strings in the input are of same and fixed length.</li>
<li>"name" field in the input json is unique.</li>
<li>In case of non-silent mutation indicate it with an "*" suffixed to the name in the trace path </li>
</ul>
<h3 id="trace-string-format">Trace String format</h3>
<pre><code><span class="token punctuation">(</span>genome<span class="token operator">-</span>name<span class="token punctuation">)</span><span class="token punctuation">(</span><span class="token operator">*</span> <span class="token punctuation">[</span><span class="token keyword">if</span> non<span class="token operator">-</span>silent mutation<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">(</span>white<span class="token operator">-</span>space<span class="token punctuation">)</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token punctuation">(</span>genome<span class="token operator">-</span>name<span class="token punctuation">)</span><span class="token punctuation">(</span><span class="token operator">*</span> <span class="token punctuation">[</span><span class="token keyword">if</span> non<span class="token operator">-</span>silent mutation<span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">(</span>white<span class="token operator">-</span>space<span class="token punctuation">)</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token operator">...</span></code></pre><h3 id="sample-inputoutput">Sample Input/Output</h3>
<h4 id="post-endpoint">Post Endpoint</h4>
<p><code>/contact_trace</code></p>
<h4 id="input-1">Input #1</h4>
<pre><code><span class="token punctuation">{</span>
    <span class="token string">"infected"</span><span class="token operator">:</span> <span class="token punctuation">{</span>
        <span class="token string">"name"</span><span class="token operator">:</span><span class="token string">"orange"</span><span class="token punctuation">,</span>
        <span class="token string">"genome"</span><span class="token operator">:</span><span class="token string">"acg-gcu-uca-gca-acu-ccc-gua-acg-gcu-uca-gca-acu-cac-gaa"</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token string">"origin"</span><span class="token operator">:</span> <span class="token punctuation">{</span>
        <span class="token string">"name"</span><span class="token operator">:</span><span class="token string">"turquoise"</span><span class="token punctuation">,</span>
        <span class="token string">"genome"</span><span class="token operator">:</span><span class="token string">"acg-gcu-uca-gca-acu-ccc-gua-acg-gcu-uca-gca-acu-cac-gaa"</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token string">"cluster"</span><span class="token operator">:</span><span class="token punctuation">[</span>
        <span class="token punctuation">{</span>
            <span class="token string">"name"</span><span class="token operator">:</span><span class="token string">"magenta"</span><span class="token punctuation">,</span>
            <span class="token string">"genome"</span><span class="token operator">:</span><span class="token string">"acg-gcu-uca-gca-acu-ccc-gua-acg-gcu-uca-gca-acu-cac-gaa"</span>
        <span class="token punctuation">}</span>
    <span class="token punctuation">]</span>
<span class="token punctuation">}</span></code></pre><h4 id="output-1">Output #1</h4>
<pre><code><span class="token punctuation">[</span>
    <span class="token string">"orange -&gt; magenta"</span><span class="token punctuation">,</span> 
    <span class="token string">"orange -&gt; turquoise"</span>
<span class="token punctuation">]</span></code></pre><h5 id="explanation">Explanation</h5>
<ul>
<li>All genomes of infected, origin, and cluster ones in the above test case are all same which means the infected could 
be contacted the virus either from "magenta" or from "turquoise". Hence the output.</li>
</ul>
<h4 id="input-2">Input #2</h4>
<pre><code><span class="token punctuation">{</span>
    <span class="token string">"infected"</span><span class="token operator">:</span> <span class="token punctuation">{</span>
        <span class="token string">"name"</span><span class="token operator">:</span><span class="token string">"plastic"</span><span class="token punctuation">,</span>
        <span class="token string">"genome"</span><span class="token operator">:</span><span class="token string">"acg-gcu-uca-gca-acu-ccc-gua-acg-gcu-uca-gca-acu-cac-gaa"</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token string">"origin"</span><span class="token operator">:</span> <span class="token punctuation">{</span>
        <span class="token string">"name"</span><span class="token operator">:</span><span class="token string">"metal"</span><span class="token punctuation">,</span>
        <span class="token string">"genome"</span><span class="token operator">:</span><span class="token string">"acg-acu-uca-gca-acu-ccc-gua-acg-ccu-uca-gca-acu-cac-gac"</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token string">"cluster"</span><span class="token operator">:</span><span class="token punctuation">[</span>
        <span class="token punctuation">{</span>
            <span class="token string">"name"</span><span class="token operator">:</span><span class="token string">"thread"</span><span class="token punctuation">,</span>
            <span class="token string">"genome"</span><span class="token operator">:</span><span class="token string">"acg-acu-uca-gca-acu-ccc-gua-acg-ccu-uca-gca-acu-cac-gaa"</span>
        <span class="token punctuation">}</span>
    <span class="token punctuation">]</span>
<span class="token punctuation">}</span></code></pre><h4 id="output-2">Output #2</h4>
<pre><code><span class="token punctuation">[</span><span class="token string">"plastic* -&gt; thread -&gt; metal"</span><span class="token punctuation">]</span></code></pre><h5 id="explanation-1">Explanation</h5>
</div>
