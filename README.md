Download Link: https://assignmentchef.com/product/solved-csci-2270-homework7-binary-search-trees-ii
<br>
This assignment builds off of the previous one conceptually, although the data structure is fundamentally different. Make sure to use the ​<strong><em>MovieTree.hpp</em></strong>​ file uploaded on Moodle for assignment 7,​<strong> not </strong>​the ​<strong><em>MovieTree.hpp</em></strong>​ of the previous assignment 6. As usual, ​<strong>do not </strong>​modify the header file. ​<em>You may implement helper functions in your .cpp file to facilitate recursion if you want as long as you don’t add those functions to the MovieTree class</em>​.

MovieTree Class

Your task is to implement a binary search tree of linked lists of movies.​ ​<em>Disclaimer: this diabolical super data structure is not practical; it is meant to challenge you and improve your skills manipulating and traversing BST’s and LL’s.</em>​ Tree nodes will contain a letter of the alphabet and a linked list. The linked list will be an alphabetically sorted list of movies which start with that letter. For example:




<strong> </strong>

<strong>MovieTree() </strong>

<ul>

 <li>Constructor: Initialize any member variables of the class to default</li>

</ul>

<strong>~MovieTree() </strong>

<ul>

 <li>Destructor: Free all memory that was allocated</li>

</ul>

<h2>void printMovieInventory()</h2>

➔ Print every movie in the data structure in alphabetical order of titles using the following format. For TreeNode ​<strong>t </strong>and LLMovieNode ​             ​<strong>m</strong>​:

<strong>// for every TreeNode (t) in the tree </strong><strong>cout</strong>​ ​&lt;&lt;​ ​”Movies starting with letter: “​ ​&lt;&lt;​ ​t-&gt;titleChar​ ​&lt;&lt;​ ​<strong>endl; </strong>

<strong>// for every LLMovieNode (m) attached to t </strong>

<strong>cout</strong>​ ​&lt;&lt;​ ​” &gt;&gt; “​ ​&lt;&lt;​ ​m-&gt;title &lt;&lt;​ ​” “​ ​&lt;&lt; m-&gt;rating &lt;&lt;​ <strong>endl;</strong>​




<strong><u>Sample output format</u> </strong>

Movies starting with letter: ​B  &gt;&gt; ​Bowling for Columbine 8

Movies starting with letter: ​D

&gt;&gt; ​Dancin’ Outlaw 8.1

&gt;&gt; ​Dogtown and Z-Boys 7.7

&gt;&gt; ​Down from the Mountain 7.4




<h2>void addMovie(int ​ranking​, std::string ​title​, int ​year​, float ​rating​)</h2>

➔ Add a movie to the data structure in the correct place based on its ​<strong>title</strong>​.

◆ If there is no tree node corresponding to the first letter of <strong>title</strong>​ , create it and insert​ it in the tree in the alphabetically correct position

◆ Create a linked list node with ​<strong>ranking</strong>​,​<strong> title</strong>​,​<strong> year </strong>​and​ ​<strong>rating</strong>​,​ ​and insert it in the linked list associated with the tree node associated with the first letter of <strong>title</strong>​ . The​ linked list must also be in alphabetical order, such that for each ​<strong>node, </strong>

<strong>node-&gt;title &lt; node-&gt;next-&gt;title </strong>

<em>Hint: you can compare strings with &lt;, &gt;, ==, etc. </em>​Also, you may assume that no two movies have​ the same title

<h2>void deleteMovie(std::string ​title​)</h2>

➔ Delete the linked list node that contains ​<strong>title</strong>​. If as a result of this deletion, the linked list becomes empty, delete the associated tree node. If the movie does not exist in the data structure, print the following message

<strong>cout</strong>​ &lt;&lt; ​”Movie: ” ​&lt;&lt; title &lt;&lt; ​” not found, cannot delete.”​ &lt;&lt; ​<strong>endl</strong>​;

<h1>Driver</h1>

Your main function should first read information about each movie from a file and store that information in a MovieTree object. <strong>The name of the file with this information should be</strong>​ <strong> passed in as a command-line argument.</strong> An example file is ​               <em>Movies.csv</em>​       ​ on Moodle. It is in the format:

&lt;Movie 1 ranking&gt;,&lt;Movie 1 title&gt;,&lt;Movie 1 year&gt;,&lt;Movie 1 rating&gt; &lt;Movie 2 ranking&gt;,&lt;Movie 2 title&gt;,&lt;Movie 2 year&gt;,&lt;Movie 2 rating&gt;

Etc…

<em>Note: For autograding’s sake, insert the nodes to the tree in the order they are read in</em>​.​<strong> After </strong>reading in the information on each movie from the file, display a menu to the user.

<strong>cout</strong>​ &lt;&lt; ​”======Main Menu======”​ &lt;&lt; ​<strong>endl</strong>​; <strong>cout</strong>​ &lt;&lt; ​”1. Print the inventory”​ &lt;&lt; ​<strong>endl</strong>​; <strong>cout</strong>​ &lt;&lt; ​”2. Delete a movie”​ &lt;&lt; ​<strong>endl</strong>​; <strong>cout</strong>​ &lt;&lt; ​”3. Quit”​ &lt;&lt; ​<strong>endl</strong>​;

The options should have the following behavior:

<h2>        ●    Print the inventory: ​Call your tree’s ​printMovieInventory​ ​function</h2>

<ul>

 <li><strong>Delete a movie: </strong>Call your ​ <strong>deleteMovie</strong>​    function on a title specified by the user. Prompt​         the user for a movie title using the following code:</li>

</ul>

<strong>cout</strong>​ &lt;&lt; ​”Enter a movie title:”​ &lt;&lt; ​<strong>endl</strong>​;

<ul>

 <li><strong>Quit: </strong>​Exit after printing a friendly message to the user:</li>

</ul>

<strong>cout</strong>​ &lt;&lt; ​”Goodbye!”​ &lt;&lt; ​<strong>endl</strong>​;


