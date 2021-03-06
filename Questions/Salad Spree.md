<div id="wrapper">
    <h1 id="sorting">Salad Spree</h1>
    <h4 id="description">Background</h4>
    <p> Meet Tom, software developer by profession, but only because noone has figured out how to make a living out of his favourite hobbies, consuming salad and being lazy. <br>
        Tom will go to the greatest lengths to not move a muscle in his body, rumour has it that he went a month without eating because the dishes weren't clean. <br>
        While he wears his laziness like a badge of honour, he has recently discovered that it's possible to be lazy and healthy at the same time. <br>
        Tom has discovered that the miracle food - 'Salad' is the panacea to all his problems. He can consume nearly infinite amounts of it while putting on no weight. <br>
    </p><h4 id="problem">Problem</h4>
        Alas, there still is a thorn in his plan, he needs to walk to stores to buy the amounts of salads he requires, and due to recent food shortages, each store that sells salads is only selling one salad per customer. <br>
        Tom is also incredibly miser and wants to make sure that he spends the least amount of money possible procuring his salads. <br>
        He has crafted an intelligent plan and decided that he will only buy salad from stores that are next to each other, that way he minimises the walking that he needs to do. <br>
        However, all this thinking has rendered Tom too tired and therefore he has hired you to write a program which will tell him the least amount of money he would need to spend to buy the number of salads he needs from consecutive stores. <br>
        Tom is too lazy and if there aren't enough consecutive stores selling the number of salads he needs, he will not buy any salads, therefore your solution should return 0 in that case. <br>
    <p></p>
    <h4 id="endpoint">Endpoint</h4>
    <p>Provide a
        <code>POST</code> endpoint
        <code>/salad-spree</code> that given 1 set of input will return 1 set of output</p>
    <h4 id="input">Input</h4>
    <p>The
        <code>HTTP POST</code> request will come with a body of
        <code>Content-Type: application/json</code> .</p>
    <pre>{
    "number_of_salads" : <b><i>n</i></b>,
    "salad_prices_street_map" : <b><i>S</i></b> (S is an array of arrays where each array indicates the price of salads in each store on a certain street. A price of "X" indicates that the store doesn't sell salads)
}</pre>
    <h4 id="output">Output</h4>
    <p>The expected
        <code>HTTP</code> response will come with a body of
        <code>Content-Type: application/json</code>
        containing</p>
    <pre>{
    result : (The minimum amount of money that Tom needs to spend to buy <b><i>n</i></b> salads from <b><i>n</i></b> consecutive stores that sell salad)
}</pre>
    <h4>Constraints</h4>
    <ul>
        <li>
            1 ≤ <b><i>n</i></b> ≤ <b><i>size of each array inside S</i></b> ≤ 100
        </li>
        <li>
            HTTP Request Timeout: 500 milliseconds
        </li>
    </ul>
        i.e. You should be expecting the number of required salads to be smaller or equal to the number of shops per street. Both of these numbers should not exceed 100.
    <h4 id="Explanation">Examples</h4>
    <p>Sample Input 1</p>
    <pre>{
    "number_of_salads" : 3,
    "salad_prices_street_map" : [["12", "12", "3", "X", "3"], ["23", "X", "X", "X", "3"], ["33", "21", "X", "X", "X"], ["9", "12", "3", "X", "X"], ["X", "X", "X", "4", "5"]]
}</pre>
<p>Sample Output 1</p>
<pre>{
"result": 24
}</pre>
<p>Explanation 1</p>
    <p>The solution in this case is on the 4th street, with 9, 12 and 3 being the lowest possible combination of three consecutive shops to buy salad from.</p>
    <p>Sample Input 2</p>
    <pre>{
    "number_of_salads" : 3,
    "salad_prices_street_map" : [["X", "X", "2"], ["2", "3", "X"], ["X", "3", "2"]]
}</pre>
<p>Sample Output 2</p>
<pre>{
"result": 0
}</pre>
<p>Explanation 2</p>
    <p>Your solution should return 0, since no street has three consecutive stores that sell salads.</p>
    <p>Sample Input 3</p>
    <pre>{
    "number_of_salads" : 2,
    "salad_prices_street_map" : [["2", "3", "X", "2"], ["4", "X", "X", "4"], ["3", "2", "X", "X"], ["X", "X", "X", "5"]]
}</pre>
<p>Sample Output 3</p>
<pre>{
"result": 5
}</pre>
<p>Explanation 3</p>
    <p>Even though there is more than one solution, the correct answer is still 5.</p>
</div>
