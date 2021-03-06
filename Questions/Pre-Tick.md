<body>
    <h1>Pre-Tick</h1>
    <p>A trader is trying to predict accurately the future price of an instrument such as a share or forex in this period of volatility. To start off, the trader does not need to predict the far future but just if the instrument will increase or decrease in price for the next tick. For that to happen, the trader will need your help to build the model.</p>
    <h2>Objective</h2>
    <p>Build an endpoint <i>/pre-tick</i> that will receive 2000 records of an instrument in chronological order.</p>
    <p>The data provided will be in csv format with ',' as separator and '\n' as line delimiter.</p>
    <p>There is no limit on the type of algorithm allowed for the model. Feel free to use machine learning if desired.</p>
    <p>Predict the close price of the instrument in the next tick.</p>
    <h3>Sample Input</h3>
    <div>
        <p>"Open,High,Low,Close,Volume</p>
        <p>867.4,873.1,862.9,873.1,761.0</p>
        <p>914.9,924.6,911.1,917.9,741.0"</p>
    </div>
    <h3>Expected Output</h3>
    <p>"920.5"</p>

</body>
