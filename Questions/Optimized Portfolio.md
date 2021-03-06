<body>
    <h1>Optimized Portfolio</h1>
<h2>Portfolio Hedging Optimization</h2>
<h4>Problem Statement</h4>
<p>You would be given Portfolio Data and a set of Index Futures Data to determine, which Index Future contract should be used to hedge the Portfolio and reduce the risk in an optimized manner. Index Future with the lowest optimal hedge ratio should be used as Optimized hedged position for the portfolio. If there are multiple future positions with the same Optimal Hedge Ratio, it should further be filtered on the lowest Futures Prc volatility. If still there are multiple records, filter based on lowest number of futures contract, to find the single fit.</p>
<h5>Formulae to be used:</h5>
<ol>
<li>Optimal Hedge Ratio = ρ X (σs / σp)</li>
</ol>
<p>Where:</p>
<p>ρ = The correlation coefficient of the changes in the spot and futures prices</p>
<p>σs = Standard deviation of changes in the spot price ‘s’</p>
<p>σp = Standard deviation of changes in the futures price ‘f’</p>
<p>An optimal hedge ratio is an investment risk management ratio that determines the percentage of a hedging instrument, i.e., a hedging asset or liability that an investor should hedge. As the hedge ratio approaches a value closer to 1, the established position is said to be “fully hedged.” <br>
On the other hand, as the hedge ratio approaches a value closer to 0, it is said to be an “unhedged” position. So, a value of 0.4 indicates that only 40% of Portfolio Value needs hedging.</p>
<ol>
<li>Number of Futures Contract = Optimal Hedge Ratio * (Portfolio value)/ (Futures contract size)</li>
</ol>
<p>where, Futures contract size = Futures Price * Notional Value of Portfolio</p>
<h4>Input Description:</h4>
<ol>
<li>
<p>For the Portfolio, following will be given:<br>
      Portfolio Name<br>
      Value<br>
      Underlying Spot Price volatility</p>
</li>
<li>
<p>For Index Future, following will be given:<br>
      Index Future name<br>
      Correlation Coefficients between Portfolio and the Index Future<br>
      Volatility of the Index Future Price<br>
      Price of the Index Future<br>
      Notional Value of the portfolio per Futures Contract</p>
</li>
</ol>
<h4>Output Description:</h4>
<ul>
<li>For the Given input Portfolio, find the Index Future, Optimal Hedge Ratio and Number of Futures Contract, which provides best hedging and lowest risk. </li>
<li>Number of futures contract should use ROUND to the nearest whole number.</li>
<li>Optimal Hedge ratio should use ROUND to 3 decimal places.</li>
</ul>
<h4>Requirements:</h4>
<ul>
<li>Expose a POST method with endpoint /optimizedportfolio</li>
<li>Return output result as json in the required format</li>
<li>Algorithm used should be optimized and sufficiently fast to enumerate results in split seconds </li>
</ul>
<h4>Constraints:</h4>
<ul>
<li>Write an optimized solution as total timeout for all the test cases in single evaluation is up to 30 secs.</li>
</ul>
<h5>Sample Input:</h5>
<pre class="codehilite"><code class="language-json">{
    "inputs": [
            {
                "Portfolio":{"Name":"Portfolio_Unhedged","Value":200000000,"SpotPrcVol":0.75},
                "IndexFutures": 
                [
                    {"Name":"Index_Fut_A","CoRelationCoefficient":0.75, "FuturePrcVol":0.95, "IndexFuturePrice":20.5, "Notional": 100000},
                    {"Name":"Index_Fut_B","CoRelationCoefficient":0.25, "FuturePrcVol":0.85, "IndexFuturePrice":15.5, "Notional": 100000}
                ]
            }
    ]
}</code></pre>

<h5>Sample Output:</h5>
<pre class="codehilite"><code class="language-json">{
    "outputs": [
            {"HedgePositionName":"Index_Fut_B","OptimalHedgeRatio":0.221, "NumFuturesContract":29}
    ]
}</code></pre>

<p><strong>NOTE</strong>: <br>
This is a sample, input could be large data having multiple records.<br>
Accordingly, output too will have multiple values.</p>
  
</body>
