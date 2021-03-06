<body style="padding:1em">
<h1 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.6em;border-bottom:1pt solid #DDDDDD;">Snakes &amp; Ladders, Smoke &amp; Mirrors</h1>
<h2 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.5em;border-bottom:1px solid #EEEEEE;">How To Play</h2>
<p style="margin:1.2em 0;">Snakes &amp; Ladders, Smoke &amp; Mirrors is an extension of regular Snakes &amp; Ladders game.</p>
<p style="margin:1.2em 0;">It is played with a single six-sided die.</p>
<p style="margin:1.2em 0;">Beside the jumps Snakes and Ladders, there are two additional jumps, Smoke and Mirror, on the board.</p>
<ul style="list-style-type:disc;margin-left:1em;padding-left:0.5em;text-indent:0;">
    <li>Smoke
        <ul style="list-style-type:circle;margin-left:0.5em;padding-left:0.5em;text-indent:0;">
            <li>Roll the die again, and move <em>backwards</em> by that value (like how Snake moves backwards).</li>
        </ul>
    </li>
    <li>Mirror
        <ul style="list-style-type:circle;margin-left:0.5em;padding-left:0.5em;text-indent:0;">
            <li>Roll the die again, and move <em>forwards</em> by that value (like how Ladders moves forwards).</li>
        </ul>
    </li>
</ul>
<p style="margin:1.2em 0;">The game ends when a player reaches the end.</p>
<p style="margin:1.2em 0;">If the player overshoots, the player will move backwards by the extra steps.</p>
<p style="margin:1.2em 0;">For example, if the board is 10x10, the player is on square <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">99</code> and rolled <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">2</code>, the final square will still be <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">99</code> (given <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">(100 - (99 + 2 - 100))</code>).</p>
<p style="margin:1.2em 0;">This version of the game <em>does not</em> grant an additional die roll when a six (6) is rolled.</p>
<h2 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.5em;border-bottom:1px solid #EEEEEE;">Objective</h2>
<p style="margin:1.2em 0;">Given a board and number of players, you will return a list of die rolls such that the game ends with the <em>last</em> player winning.</p>
<p style="margin:1.2em 0;">Upon a successful play with the die rolls, a score of <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">(board size) / (number of squares landed)</code> will be given.</p>
<p style="margin:1.2em 0;">Otherwise, the score is 0.</p>
<p style="margin:1.2em 0;">We will do a <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">POST</code> request on your team URL with the endpoint <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">/slsm</code>.</p>
<h2 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.5em;border-bottom:1px solid #EEEEEE;">Scoring</h2>
<p style="margin:1.2em 0;">Your solution will be evaluated (i.e. played) twelve times with varying difficulty levels, which are added to give a raw score.</p>
<p style="margin:1.2em 0;">If the last player wins all games, the raw score will be divided by two and be at least 20, else the raw score will be divided by four, to arrive at the final score.</p>
<p style="margin:1.2em 0;">The maximum point is 100, before factoring in challenge difficulty weightage.</p>
<h2 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.5em;border-bottom:1px solid #EEEEEE;">Constraints</h2>
<ul style="list-style-type:disc;margin-left:1em;padding-left:0.5em;text-indent:0;">
    <li>Board size, <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">boardSize</code>, is a product of width and height, which will each be between <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">8</code> and <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">20</code>, inclusive.</li>
    <li>Number of players, <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">players</code>, will be between <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">2</code> and <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">8</code>, inclusive.</li>
    <li>Squares are <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">1</code>-based, so the first square is <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">1</code> and the last square will be <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">width * height</code>.</li>
    <li>Both the first and last squares will not be the start or end of any jump.</li>
    <li>A Smoke will not appear before the sixth square (so that the second die roll will not go beyond the first square).</li>
    <li>A Mirror will not appear within the last six squares (so that the second die roll will not go beyond the last square).</li>
    <li>None of the jumps' squares will conflict with one another.</li>
    <li>There will be at least one of each jump.</li>
</ul>
<h2 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.5em;border-bottom:1px solid #EEEEEE;">Sample input</h2>
<pre style="font-family:Consolas,Inconsolata,Courier,monospace;font-size:1em;line-height:1.3em;margin:1.2em 0;"><code style="background-color:#f8f8f8;border-radius:3px;border:1px solid #ccc;display:block;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;margin:0 0.15em;overflow:auto;padding:0.5em 0.7em;white-space:pre;color:#444;">{"boardSize":100,"players":4,"jumps":["59:39","9:37","42:0","0:3"]}
</code></pre>
<p style="margin:1.2em 0;">Explanation:</p>
<ul style="list-style-type:disc;margin-left:1em;padding-left:0.5em;text-indent:0;">
    <li>Board size: 100</li>
    <li>Players: 4</li>
    <li>Jumps (directions are important!):
        <ul style="list-style-type:circle;margin-left:0.5em;padding-left:0.5em;text-indent:0;">
            <li>Snake: From <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">59</code> to <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">39</code></li>
            <li>Ladder: From <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">9</code> to <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">37</code></li>
            <li>Smoke: From <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">42</code> to <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">-&lt;0&gt;</code>, <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">&lt;0&gt;</code> being a die roll placeholder (direction <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">42:0</code> resembling a Snake)</li>
            <li>Mirror: From <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">3</code> to <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">+&lt;0&gt;</code>, <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">&lt;0&gt;</code> being a die roll placeholder (direction <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">0:3</code> resembling a Ladder)</li>
            <li>Usage of <code style="background-color:#f8f8f8;border-radius:2px;padding:1px 2px 0 2px;border:1px solid #e0e0e0;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;color:#444;">0</code> as a die roll placeholder is to facilitate parsing of values as integers</li>
        </ul>
    </li>
</ul>
<h2 style="margin:1.3em 0 1em;padding:0;font-weight:bold;font-size:1.5em;border-bottom:1px solid #EEEEEE;">Sample output</h2>
<pre style="font-family:Consolas,Inconsolata,Courier,monospace;font-size:1em;line-height:1.3em;margin:1.2em 0;"><code style="background-color:#f8f8f8;border-radius:3px;border:1px solid #ccc;display:block;font-family:Consolas,Inconsolata,Courier,monospace;font-size:0.9em;margin:0 0.15em;overflow:auto;padding:0.5em 0.7em;white-space:pre;color:#444;">[1, 2, 3, 4, 5, 6]
</code></pre>
<p style="margin:1.2em 0;">A list of die rolls.</p>
</body>
