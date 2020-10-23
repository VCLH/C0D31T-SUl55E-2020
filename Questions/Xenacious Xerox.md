<body>
    <h1>Xenacious Xerox</h1>

<p>Ron is a CS employee in charge of our Xerox machines (one must imagine Ron happy).</p>

<blockquote>
<p>The copier, it's the beating heart of any business — James Morgan McGill.</p>
</blockquote>

<p>Ron's job is crucial, no company works properly without a sound copier workflow. You've been hired as Ron's deputy to help him figure out how to deliver the maximum bang (pages) for the buck (time). Optimize your algorithm to schedule printing jobs as quickly as you can following the given requirements.
There are M A3 printers and N A4-only printers, A3 printers can print A4 documents too.
A3 xeroxes spend 2 seconds per A4 page, and 5 seconds per A3 page.
A4 xeroxes spend 3 seconds per A4 page.</p>

<p>A3 Xerox machines are labelled M0, M1, ..., Mx-1 with x the number of A3 copiers.
A4 Xerox machines are labelled N0, N1, ..., Ny-1 with y the number of A4 copiers.
You may use larger indexes, but note that the indexes will be modulo x or y.</p>

<h2>Input</h2>

<p>Your application will receive a problem in the following JSON format:
<code>json
{
  "num_of_a3_copiers": 42,
  "num_of_a4_copiers": 24,
  "documents": {
    "document-name": { "num_of_pages": 200, "page_format": "A4" },
    "other-document": { "num_of_pages": 100, "page_format": "A3" }
  }
}
</code></p>

<p>This payload will be sent as a POST on the <code>/xerox</code> endpoint.</p>

<h2>Output</h2>

<p>Each response should have the following JSON format:</p>

<p><code>json
{
  "document-id": [
    {
      "from": 1,
      "to": 100,
      "copier": "M1"
    },
    {
      "from": 101,
      "to": 200,
      "copier": "M2"
    }
  ]
}
</code></p>

<p>The ranges from/to are inclusive.</p>

<p>All the documents have to be printed in full for your submission to be accepted.
You may print a page more than once. (Although I'm not sure why you would want to do that, think about the trees.)</p>

</body>
