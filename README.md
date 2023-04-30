Download Link: https://assignmentchef.com/product/solved-ics2205-assignment-2
<br>
<h2>Analytics</h2>

The aim of this task is to use the given Twitter dataset and to perform some analyses on the underlying <em>mention </em>graph (explained below). The dataset is presented in a raw format and as a <em>tab-separated-values </em>file and is a subset of a larger twitter dataset that was collected between June 2009 and December 2009. Each line contains a tweet and consists of three tab-separated fields. These include a timestamp, the alias of the user that sent the tweet and the tweet content itself.

This is a typical entry in the file:

<em>2009-06-11 17:07:59 drew @jack Whens it coming to the iPhone? Or is it?</em>.

Users might <em>mention </em>other users in their tweets by using the <em>@ </em>symbol followed by the name of the other user, such as <em>@jack </em>in the example. Multiple other users might be mentioned. The <em>mention </em>graph is therefore a directed graph where the vertices are the users and the edges represent the mentions. Thus <em>userA </em>− [<em>mentions</em>]− <em>&gt; userB</em>. The number of times that <em>userA </em>mentions <em>userB </em>can be transformed into a weight. You do not need to consider the time when creating the <em>mention </em>graph.

You need to do the following (marks are allocated to each part out of 100%):

<ol>

 <li>Extract the mention graph from the Twitter data (<strong>marks 20%</strong>):

  <ul>

   <li>parse the <em>.tsv </em>file using Python to get the individual tweets; generate the adjacency list for each user based on the alias. A user is adjacent to another user if he/she is mentioned in a tweet. Keep track of the number of times that some <em>userA </em>mentions <em>userB</em>;</li>

   <li>use the adjacency list to create the <em>mention </em>graph in NetworkX. Use the counts as weights on the edges;</li>

   <li>in the jupyter notebook provide information about any challenges that you might have encountered when parsing and cleaning the data and when creating the graph, and how you solved them. Discuss as well any decisions that you might have made.</li>

  </ul></li>

 <li>To start analysing the underlying structure of the graph, compute thefollowing statistics for the graph (<strong>marks 30%</strong>):

  <ul>

   <li>number of nodes and edges;</li>

   <li>indegree and outdegree;</li>

   <li>degree distribution;</li>

   <li>average path length;</li>

   <li>global clustering coefficient.</li>

  </ul></li>

</ol>

In the jupyter notebook provide information about any challenges that you might have encountered when computing these statistics, and how you solved them. Is the graph connected? Are there “giant” components<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> in the graph? What can you say about the graph based on the computed statistics?

<ol start="3">

 <li>Determine the top 10 users (<strong>marks 30%</strong>): based on the degree, closeness and betweenness centrality measures. You need to deal with directionality to facilitate computation. Discuss how you did this.</li>

 <li>Visualise the graph (or the most important components) (<strong>marks 20%</strong>): use some size-color-valuation scheme, whereby nodes with higher centrality (say betweenness) will have a specific color and size. The user’s alias can be used as the node label and the edge width can represent the weight (based on mention counts).</li>

</ol>

This task is being allocated a total of <strong>50 marks</strong>.

<h2>1.2         Task 2: Information Retrieval</h2>

For this task, you are to use the <em>WES </em>dataset available from <a href="http://pikes.fbk.eu/ke4ir">http://pikes. </a><a href="http://pikes.fbk.eu/ke4ir">fbk.eu/ke4ir</a> to build a simple Information Retrieval engine that uses the Vector Space model to find documents related to a user query. You need to use the following files from the dataset:

<ul>

 <li>The document collection – <a href="https://knowledgestore.fbk.eu/files/ke4ir/docs-raw-texts.zip">https://knowledgestore.fbk.eu/files/ </a><a href="https://knowledgestore.fbk.eu/files/ke4ir/docs-raw-texts.zip">ke4ir/docs-raw-texts.zip</a><a href="https://knowledgestore.fbk.eu/files/ke4ir/docs-raw-texts.zip">;</a> and</li>

 <li>The set of queries – <a href="https://knowledgestore.fbk.eu/files/ke4ir/queries-raw-texts.zip">https://knowledgestore.fbk.eu/files/ke4ir/ </a><a href="https://knowledgestore.fbk.eu/files/ke4ir/queries-raw-texts.zip">queries-raw-texts.zip</a><a href="https://knowledgestore.fbk.eu/files/ke4ir/queries-raw-texts.zip">.</a></li>

</ul>

Both of these files are being made available on the VLE.

An IR engine consists of TWO parts – the document indexing part, and the querying component.

For the document indexing part, you need to implement these process steps:

<ol>

 <li>Parse the document to extract the data in the XML’s <em>&lt; raw &gt; </em>tag;</li>

 <li>Tokenise the documents’ content;</li>

 <li>Perform case-folding, stop-word removal and stemming;</li>

 <li>Build the term by document matrix containing the <em>IDF </em>weight for each term within each document.</li>

</ol>

For the querying component, you need to implement the following process steps:

<ul>

 <li>Get a user query – note that it can be set within the notebook, directly into a variable named <em>query</em>;</li>

 <li>Preprocess the user query (tokenisation, casefolding, stop-word removal and stemming);</li>

 <li>Use cosine similarity to calculate the similarity between the query and each document returned in the previous step;</li>

 <li>Output the list of documents as a ranked list.</li>

</ul>

Note that you can use <em>NLTK </em>or any other library to help in the tokenisation and preprocessing of the text. However, you <strong>need </strong>to implement your own <strong>TF.IDF </strong>weighting and <strong>Cosine Similarity </strong>measures.

This task is being allocated <strong>50 marks</strong>. The marks are distributed as follows:

<ul>

 <li>Indexing part:

  <ul>

   <li>Document parsing – <strong>5 marks</strong>;</li>

   <li>Extraction of index terms – <strong>10 marks</strong>;</li>

   <li>Weighting of index terms (term-by-document matrix) – <strong>15 marks</strong>;</li>

  </ul></li>

 <li>Querying part:

  <ul>

   <li>Query processing – <strong>2 marks</strong>;</li>

   <li>Calculated similarity between the query and each document – <strong>13 marks</strong>;</li>

   <li>Building and outputting the ranked list of relevant documents – <strong>5 marks</strong>.</li>

  </ul></li>

</ul>

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="https://jupyter.org/">https://jupyter.org/</a>

<a href="#_ftnref2" name="_ftn2">[2]</a> A giant component is a connected component of a network that contains a significant proportion of the entire nodes in the network. Typically as the network expands the giant component will continue to have a significant fraction of the nodes.