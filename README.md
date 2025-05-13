# concurrency-parallelism-project-8-solved
**TO GET THIS SOLUTION VISIT:** [Concurrency-Parallelism Project 8 Solved](https://www.ankitcodinghub.com/product/concurrency-parallelism-project-8-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;94293&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Concurrency-Parallelism Project 8 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
With this lab assignment you will understand the technical difficulties and limi- tations of the use of locks for synchronising multiple processes/threads accessing a shared complex data structure.

1 Ob jectives

In this project you are provided with a running Java application downloadable from Bit- Bucket

<pre>  git clone https://bitbucket.org/joaomlourenco/article-rep.git
</pre>
This application accept a command line argument with eight parameters to control its behaviour. The application is correct only when executed single-threaded. Appropriate synchronisation must be added for the application to work correctly in a multi-threading setting.

The application simulates a repository of scientific articles. Each article has a title, a set of co-authors and a set of keywords. The application uses three hash maps to implement this repository as an “in-memory database”: one hash-map to keep the articles’ information (byArticleId), another hash-map to map authors to articles (byAuthor), and a third hash-map to map keywords to articles (byKeyword). These hash maps are defined as:

private Map&lt;Integer , Article&gt; byArticleId ; private Map&lt;String , List&lt;Article&gt;&gt; byAuthor; private Map&lt;String , List&lt;Article&gt;&gt; byKeyword;

where the hashmap byArticleId maps integers (the article identifier) to articles; the hashmap byAuthor maps author names to a list of papers authored by that author; and the hashmap byKeyword maps keywords to a list of papers assigned with that keyword.

</div>
</div>
<div class="layoutArea">
<div class="column">
The article constructor is defined as:

public Article ( int id , String name) { this.id = id;

this .name = name;

this . authors = new LinkedList&lt;String &gt;(); this.keywords = new LinkedList&lt;String&gt;();

}

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
where the id is a unique identifier for the paper, the name is the title of the paper, and both authors and keywords are lists with the author names and keywords respectively.

The behaviour of the application is configurable by arguments in the command line (8 obligatory arguments). The application prints some statistics when terminating.

It is possible to enable periodic consistency self-checking in the application by setting a property from the command line by adding

−Dcp. articlerep . validate=true

right after the “java” in the command line. When the self-checking is active, every 5 seconds all the application threads are “suspended” and a validation thread runs a set of self- checking tests. If no problems are found the application threads are resumed, otherwise an error message is print and the application aborts.

Both with and without intermediate checking, a final self-checking is always executed when the execution terminates.

Why may the consistency self-checking fail?

References to the same object are stored in more than one data structure. When there are concurrent inserts and removes, although each the hashmap individually may be consistent, the global contents of the three hashmaps are not, e.g., it may happen that the byAuthor hashmap is referencing a paper which was already removed from the byArticleId hashmap. Think. . . how can this happen? 😉

2 Compiling and Running

To compile the application, go to the application root directory (you shall have three subdirectories: “bin”, “src”, and “resources”) and type the command:

make

To run the application from the same (compilation) directory, run the command below. It will print some info on the required command line arguments.

<pre>java -cp bin cp/articlerep/MainRep
usage: cp.articlerep.MainRep time(sec) nthreads nkeys put(%) del(%)
</pre>
<pre>                             nauthors nkeywords nfindlist
</pre>
</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
The command line arguments are:

Argument Explanation

</div>
</div>
<div class="layoutArea">
<div class="column">
time nthreads

nkeys put

del nauthors

nkeywords nfindlist

</div>
<div class="column">
for how long will the program run (in seconds).

the number of threads that will operate concurrently on the “in-memory database”.

size of the hash-map (smaller size implies more collisions).

percentage of insert operations.

percentage of remove operations.

average number of co-authors for each article (higher number implies more conflicts).

average number of keywords for each article (higher number implies more conflicts).

number of authors (or keywords) in the find list (read carefully the ex- planation of the get operation below).

</div>
</div>
<div class="layoutArea">
<div class="column">
Please notice that the percentage of get operations is calculated as: get = 100 − put − del

The lookup (get) operation works as follows:

<ul>
<li>Half the times (50% of the get operations) will do a lookup by authors. The other
half will do a lookup by keywords.
</li>
<li>Generate a set A with nfindlist authors/keywords (selected randomly from the uni- verse of authors/keywords).</li>
<li>For each author/keyword i in the set A, create a set Pi with the articles containing i as a co-author/keyword.
• Create the set P of all articles verifying the lookup condition (P = ∪Pi).

Higher values in the nfindlist argument implies more complex get operations and higher contention in the accesses to the “in-memory database”.

Example of a possible command line:

<pre>java -Dcp.articlerep.validate=true -cp bin cp/articlerep/MainRep 10 4 1000 10 10 100 100 5
</pre>
You should try with other values to acquire some sensitiveness to the effect of each parameter.

3 Workplan / Methodology

3.1 Add more invariants to the automatic validation

Study the behaviour of the data worker and the way the hash-maps are used in the appli- cation. Can you devise some additional invariants that are not being checked? If you do, you may add your new invariants to the periodic checking phase or as a final checking, jut before the application prints the statistics.

3
</li>
</ul>
</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
3.2 Add appropriate synchronisation to the program

Add appropriate synchronisation to the program. You should not change the source code logic to avoid the concurrency errors!

You must add synchronisation mechanisms in the appropriate locations for the code to run correctly. If for adding the appropriate synchronisation mechanisms you need to do small changes in the code, e.g., create new private methods, add new public methods; change the arguments of the existing methods, etc.

I suggest you make three versions of the solution:

<ol>
<li>Global lock (all three hash maps). Implement a solution using a global lock that will block the accesses to the three hash maps at the same time. This solution shall work correctly by shall not scale (and the global lock eliminates all the concurrency).</li>
<li>Global lock per hash map. Implement a solution using a global lock per hash map. Although this will ensure that each hash map individually will be consistent, the global contents of the three hash maps may be inconsistent, e.g., one hash map references an Article that is missing in the other hash maps.</li>
<li>Multiple locks per hash map (at the collision lists). This solution is harder to implement, but it shall provede both correctness and performance, exhibiting some speedup when the number of processors increase.</li>
</ol>
3.3 Evaluate the effectiveness of your synchronisation strategy

Run tests to evaluate the scalability of your solution when you increase the number of threads. Run experiments with 1, 2, 4, . . . , N threads, where N is the double of the number of processors/cores you have available in your development computer.

NOTE: if possible please run your tests in real hardware, i.e., if you are using a virtual machine (like VMWare, Virtualbox, etc) as your developing environment please copy your files to one of the computers in the lab and run the tests there.

Document History

</div>
</div>
<div class="layoutArea">
<div class="column">
Version

</div>
<div class="column">
Date

</div>
<div class="column">
Description

Revision of the text. Elimination of the unnecessary get com- mand line argument. New visual.

Clarification of the expected work in Section 3.2.

Initial version.

</div>
</div>
<div class="layoutArea">
<div class="column">
1.2 2021-05-11

1.1 2020-05-19 1.0 2020-05-19

</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
