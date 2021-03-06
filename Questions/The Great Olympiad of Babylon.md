<body><h1 id="thegreatolympiadofbabylon">The Great Olympiad of Babylon</h1>
<p>Created By Moin and Ryan </p>
<h1 id="problemstatement">Problem Statement</h1>
<p>The city of Babylon holds a International Olympiad each year inviting intellectuals from all over the world. Arsenios hails from a small village in Macedonia and has dreamt since early childhood to be able to participate in the Olympiad, which consists of questions from every book known to mankind.</p>
<p>In the year 1300BC, Arsenios is finally able to make the journey to Babylon but he only has a limited number of days to prepare for the Olympiad. He would like to ask for your help in scheduling his daily reading in order to maximize his chances of winning. </p>
<p>As such Arsenios has figured out the amount of time he has each day up until the day of the Olympiad. He also knows the amount of time in minutes it will take him to read a particular book. He will provide you this information and would be grateful if you can help him design the optimal schedule. Since the Olympiad guarantees an equal number of questions from each book, Arsenios will be able to maximize his score simply by reading the most books he can read given the constraints. He would like to ask you to tell him how many books he would be able to read with the optimal schedule given that he has to read a book to completion on the same day that he starts reading it.</p>
<h1 id="problemspecifications">Problem Specifications</h1>
<p>The number of books (<code>numberOfBooks</code>) would always be greater than the number of days available for preparation (<code>numberOfDays</code>).
The time required to read book i where <code>0 &lt;= i &lt; numberOfBooks</code> to completion is going to be provided as books<sub>i</sub> where books is a list.
The time available for reading on day j where <code>0 &lt;= j &lt; numberOfDays</code> is going to be provided as days<sub>j</sub> where days is a list.</p>
<p>The result should be the number of books Arsenios can read with the optimal schedule (<code>optimalNumberOfBooks</code>). </p>
<p>Endpoint: /olympiad-of-babylon</p>
<h2 id="inputlimits">Input Limits</h2>
<pre><code>3 &lt; numberOfDays &lt;= 10
5 &lt; numberOfBooks &lt;= 50
80 &lt;= days[i] &lt;= 120 | For all i
20 &lt;= books[i] &lt;= 80 | For all i
</code></pre>
<h2 id="inputschema">Input Schema</h2>
<pre><code>{
    numberOfBooks: Integer,
    numberOfDays: Integer,
    books: [Integer],
    days: [Integer]
}
</code></pre>
<h2 id="outputschema">Output Schema</h2>
<pre><code>{
    optimalNumberOfBooks: Integer
}
</code></pre>
<h1 id="examples">Examples</h1>
<h2 id="input">Input</h2>
<pre><code>{
    numberOfBooks: 5,
    numberOfDays: 3,
    books: [114, 111, 41, 62, 64],
    days: [157, 136, 130]
}
</code></pre>
<h2 id="ouput">Ouput</h2>
<pre><code>{
    optimalNumberOfBooks: 5
}
</code></pre>
<h2 id="potentialoptimalschedule">Potential Optimal Schedule</h2>
<pre><code>Day 1: Book 2 and Book 3 (111 minutes + 41 minutes = 152 minutes &lt; 157 minutes)
Day 2: Book 4 and Book 5 (62 minutes + 64 minutes = 126 minutes &lt; 136 minutes)
Day 3: Book 1 (114 minutes &lt; 130 minutes)
</code></pre></body>
