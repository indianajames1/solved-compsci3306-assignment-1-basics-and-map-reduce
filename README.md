Download Link: https://assignmentchef.com/product/solved-compsci3306-assignment-1-basics-and-map-reduce
<br>
Figure 1: Self-grouping

<h1>2           Assignment</h1>

<strong>Exercise 1 </strong><em>Suspected Pairs </em>

Using the information from the first lecture (or Section 1.2.3 in the textbook), what would be the number of suspected pairs if the following changes were made to the data (all changes should be applied at once).

<ol>

 <li>The number of days of observation was raised to 5000.</li>

 <li>The number of people observed was raised to 5 billion (and there were therefore 500<em>,</em>000 hotels).</li>

 <li>We only reported a pair as suspect if they were at the same hotel at the same time on four different days.</li>

</ol>

<strong>Exercise 2 </strong><em>Hadoop </em>

For this exercise, you have to set up and configure your system to use Hadoop. Follow the instructions in Stanford document at <a href="http://snap.stanford.edu/class/cs246-2017/homeworks/hw0/tutorialv3.pdf">http://snap.stanford.edu/ </a><a href="http://snap.stanford.edu/class/cs246-2017/homeworks/hw0/tutorialv3.pdf">class/cs246-2017/homeworks/hw0/tutorialv3.pdf</a> and set up the virtual machine as described in Section 1. Run the example program of Section 2 and carry out the different steps given in that section.

<ul>

 <li>Run your job on the file <a href="https://www.gutenberg.org/files/100/100-0.txt">http://www.gutenberg.org/files/100/100-0. </a><a href="https://www.gutenberg.org/files/100/100-0.txt">txt</a> in standalone mode and pseudo-distributed mode and record the output.</li>

</ul>

<strong>Exercise 3 </strong><em>Friend Recommendation System (Stanford) </em>

Write a MapReduce program in Hadoop that implements a simple People You Might Know social network friendship recommendation algorithm. The key idea is that if two people have a lot of mutual friends, then the system should recommend that they connect with each other. You have to run the program on the system setup in Exercise 2 in order to receive points for this exercise.

<strong>Input: </strong>Download the input file from the link: <a href="http://snap.stanford.edu/class/cs246-data/hw1q1.zip">http://snap.stanford.edu/ </a><a href="http://snap.stanford.edu/class/cs246-data/hw1q1.zip">class/cs246-data/hw1q1.zip</a><a href="http://snap.stanford.edu/class/cs246-data/hw1q1.zip">.</a> The input file contains the adjacency list and has multiple lines in the following format:

&lt;User&gt;&lt;TAB&gt;&lt;Friends&gt;

Here, <em>&lt;</em>User<em>&gt; </em>is a unique integer ID corresponding to a unique user and <em>&lt;</em>Friends<em>&gt; </em>is a comma separated list of unique IDs corresponding to the friends of the user with the unique ID <em>&lt;</em>User<em>&gt;</em>. Note that the friendships are mutual (i.e., edges are undirected): if A is friend with B then B is also friend with A. Algorithm: Let us use a simple algorithm such that, for each user U, the algorithm recommends <em>N </em>= 10 users who are not already friends with U, but have the most number of mutual friends in common with U.

<strong>Output</strong>: The output should contain one line per user in the following format:

&lt;User&gt;&lt;TAB&gt;&lt;Recommendations&gt;

where <em>&lt;</em>User<em>&gt; </em>is a unique ID corresponding to a user and <em>&lt;</em>Recommendations<em>&gt; </em>is a comma separated list of unique IDs corresponding to the algorithms recommendation of people that <em>&lt;</em>User<em>&gt; </em>might know, ordered in decreasing number of mutual friends. Even if a user has less than 10 second-degree friends, output all of them in decreasing order of the number of mutual friends. If there are recommended users with the same number of mutual friends, then output those user IDs in numerically ascending order. Also, please provide a description of how you are going to use MapReduce jobs to solve this problem. Do not write more than 3 to 4 sentences for this: we only want a very high-level description of your strategy to tackle this problem. Note: It is possible to solve this question with a single MapReduce job. But if your solution requires multiple map reduce jobs, then that is fine too.

For your submission

<ul>

 <li>Include your source code</li>

 <li>Include in your writeup a short paragraph describing your algorithm to tackle this problem.</li>

 <li>Include in your writeup the recommendations for the users with following user IDs: 924, 8941, 8942, 9019, 9020, 9021, 9022, 9990, 9992, 9993.</li>

</ul>

<strong>Exercise 4 </strong><em>MapReduce (15 points)</em>

This exercise has 4 parts. In this exercise, you will be writing and implementing two MapReduce programs. Both are a bit challenging, but they will help you to have a better understanding about the MapReduce implementation. After you write the programs, you will need to answer some questions about them.

Remember that neither problem is case sensitive, so transform words to lowercase or uppercase. Also remember to use the StringTokenizer to find the correct answers.

<strong>Part 1</strong>: Write a program that processes the FirstInputFile <a href="https://www.gutenberg.org/cache/epub/100/pg100.txt">http://www.gutenbe</a>rg. <a href="https://www.gutenberg.org/cache/epub/100/pg100.txt">org/cache/epub/100/pg100.txt</a> and the SecondInputFile <a href="https://www.gutenberg.org/files/3399/3399.txt">http://www.gutenb</a>erg. <a href="https://www.gutenberg.org/files/3399/3399.txt">org/files/3399/3399.txt</a><a href="https://www.gutenberg.org/files/3399/3399.txt">.</a> This program should count the number of words with a specific amount of letters in these files – for example, the number of words with 4 letters, 5 letters and so on. If one word is repeated 20 times in the text, count it individually 20 times.

<strong>Part 2</strong>: Answer Questions 1-6.

<ul>

 <li>Q1: How many words are there with length 10 in FirstInputFile?</li>

 <li>Q2: How many words are there with length 4 in FirstInputFile?</li>

 <li>Q3: What is the longest length between words and what is its frequency in FirstInputFile?</li>

 <li>Q4: How many words are there with length 2 in SecondInputFile?</li>

 <li>Q5: How many words are there with length 5 in SecondInputFile?</li>

 <li>Q6: What is the most frequent length and what is its frequency in SecondInputFile?</li>

</ul>

<strong>Part 3</strong>: Write a second program that again processes the FirstInputFile <a href="https://www.gutenberg.org/cache/epub/100/pg100.txt">http:</a>

<a href="https://www.gutenberg.org/cache/epub/100/pg100.txt">//www.gutenberg.org/cache/epub/100/pg100.txt</a> and the SecondInputFile <a href="https://www.gutenberg.org/files/3399/3399.txt">http://www.gutenberg.org/files/3399/3399.txt</a><a href="https://www.gutenberg.org/files/3399/3399.txt">.</a> However, in addition to counting the number of words with a specific amount of letters, if one word is repeated several times, count it only once. So, your output should be the frequency of words with same length, but count a repeated word only once. Note: You may need to use 2 MapReduce jobs.

<strong>Part 4</strong>: Answer Questions 7-12 below:

<ul>

 <li>Q7: How many words are there with length 10 in FirstInputFile?</li>

 <li>Q8: How many words are there with length 4 in FirstInputFile?</li>

 <li>Q9: What is the most frequent length and what is its frequency in FirstInputFile?</li>

 <li>Q10: How many words are there with length 5 in SecondInputFile?</li>

 <li>Q11: How many words are there with length 2 in SecondInputFile?</li>

 <li>Q12: What is the second-most frequent length and what is its frequency in SecondInputFile?</li>

</ul>

<strong>Exercise 5 </strong><em>Summary of 2.4 and 2.5 (10 +10 points) (</em><em>Postgraduate Students (COMP SCI 7306) only)</em>

For this exercise you have to read Section 2.3.9-2.3.11, 2.4, and 2.5 in Leskovec, Rajara- man, Ullman (second edition, 2014).

<ul>

 <li>Summarize the content of 2.4 in your own words (600 words).</li>

 <li>Summarize the content of 2.5 in your own words (600 words).</li>

</ul>

<h1>3           Procedure for handing in the assignment</h1>

Work should be handed in using Canvas. The submission should include:

<ul>

 <li>PDF file of your solutions for theoretical assignments.</li>

 <li>all source files</li>

 <li>descriptions as required in the statement of the exercises</li>

 <li>Hadoop outputs for the exercises</li>

</ul>

<em>a README.txt file containing instructions to run the code, the two group members’ names, student numbers, and email addresses of the group members, </em><strong>only one submission per group</strong>