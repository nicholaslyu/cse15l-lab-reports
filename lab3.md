## Lab Report 3 Researching Commands

In this lab, I focused on ``grep`` command. 

### Option1 

``grep -o ``

``-o`` option would display only the string that exactly match the string input you want to search for, instead of displaying all the lines that contain this string. 
**Example 1**
I run ``grep -o "plane" technical/911report/chapter-1.txt``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep -o "plane" technical/911report/chapter-1.txt
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
plane
</code></pre>
If I delete ``-o`` option from the command, it would display many more contents than right now. But with ``-o``, it only display all ``plane`` in the chosen file I am searching at. 

**Example 2**
I run ``docsearch % grep  -o "checkpoint" technical/911report/chapter-1.txt``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep  -o "checkpoint" technical/911report/chapter-1.txt
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
checkpoint
</code></pre>
Here I want to see the occurances of word ``checkpoint``. It only display the word ``checkpoint``.The result is very clear that I can save it to another file for further analysis. If without ``-o`` option, a lot of unnecessary contents would also be displayed. 

### Option2
``grep -n``
``-n`` option would display the line numbers as well as the lines that contains the input string in the file(s) we are searching for.
**Example 1**
I run ``grep -n "Bin Laden" technical/911report/*.txt ``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep -n "Bin Laden" technical/911report/*.txt        
technical/911report/chapter-11.txt:161:                terrorist leader, with the headline "U.S. Hard Put to Find Proof Bin Laden Directed
technical/911report/chapter-13.3.txt:36:                www.npr.org/display_pages/features/feature_1253796.html). 14. "Bin Laden's 'Letter
technical/911report/chapter-13.3.txt:278:                Fleecing Bin Laden," Wall Street Journal, Dec. 3, 2001, p. A1.
technical/911report/chapter-13.3.txt:392:            87. For general information on Hage, see Oriana Gill, "Hunting Bin Laden: A Portrait
technical/911report/chapter-13.3.txt:428:            93. ABC News interview, "Terror Suspect: An Interview with Osama Bin Laden," Dec. 22,
technical/911report/chapter-13.3.txt:467:                Statements of Prosecutor and Judge, United States v. Bin Laden, No. S(7) 98 Cr. 1023
technical/911report/chapter-13.3.txt:1060:                FBI Special Agent Daniel Coleman, United States v. Usama Bin Laden, No. S(7) 98 Cr.
technical/911report/chapter-13.3.txt:1457:            109. Indictment, United States v. Usama Bin Laden, No. 98 Cr. (S.D. N.Y. unsealed
technical/911report/chapter-13.4.txt:779:                Terrorism, Sudan Struck a Blow by Fleecing Bin Laden," Wall Street Journal, Dec. 3,
technical/911report/chapter-13.4.txt:1549:                Bin Laden: How Bill Clinton's Failures Unleashed Global Terror (Regnery, 2003),
technical/911report/chapter-13.4.txt:1824:                memo,"U.S. Engagement with the Taliban on Usama Bin Laden," undated (attached to NSC
technical/911report/chapter-13.5.txt:2719:            8. Tim Weiner, "U.S. Hard Put to Find Proof Bin Laden Directed Attacks," New York
technical/911report/chapter-13.5.txt:2842:                final aim is the restoration of the caliphate.'"Mehdi Mozaffari,"Bin Laden and
technical/911report/chapter-6.txt:103:                to resolve the Bin Laden problem at the earliest possible time." But Zinni came back
</code></pre>
I want to see the how many files inside ``911report`` contain the word``Bin Laden``. With ``-n`` option, I can easily trace back to the lines by looking at its line number. Very useful!

**Example 2**
I run ``grep -n "Bin Laden" technical/911report/chapter-13.3.txt``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep -n "Bin Laden" technical/911report/chapter-13.3.txt
36:                www.npr.org/display_pages/features/feature_1253796.html). 14. "Bin Laden's 'Letter
278:                Fleecing Bin Laden," Wall Street Journal, Dec. 3, 2001, p. A1.
392:            87. For general information on Hage, see Oriana Gill, "Hunting Bin Laden: A Portrait
428:            93. ABC News interview, "Terror Suspect: An Interview with Osama Bin Laden," Dec. 22,
467:                Statements of Prosecutor and Judge, United States v. Bin Laden, No. S(7) 98 Cr. 1023
1060:                FBI Special Agent Daniel Coleman, United States v. Usama Bin Laden, No. S(7) 98 Cr.
1457:            109. Indictment, United States v. Usama Bin Laden, No. 98 Cr. (S.D. N.Y. unsealed
</code></pre>
I want to see the word which lines does word ``Bin Laden`` appears in ``chapter-13.3.txt``. It displays the line number and their contents very clearly. The result for this example is also a part of the output from the previous one.

### Option3
``grep -c --count``
This option would display the number of lines that contain the input string in the searching file(s).

**Example1**
I run ``grep -c --count "defense" technical/911report/*.txt``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep -c --count "Bin Laden" technical/911report/*.txt
technical/911report/chapter-1.txt:0
technical/911report/chapter-10.txt:0
technical/911report/chapter-11.txt:1
technical/911report/chapter-12.txt:0
technical/911report/chapter-13.1.txt:0
technical/911report/chapter-13.2.txt:0
technical/911report/chapter-13.3.txt:7
technical/911report/chapter-13.4.txt:3
technical/911report/chapter-13.5.txt:2
technical/911report/chapter-2.txt:0
technical/911report/chapter-3.txt:0
technical/911report/chapter-5.txt:0
technical/911report/chapter-6.txt:1
technical/911report/chapter-7.txt:0
technical/911report/chapter-8.txt:0
technical/911report/chapter-9.txt:0
technical/911report/preface.txt:0
</code></pre>
 I want to see how many lines in each documment containing the word ``Bin Laden``. If I want to research more about ``Bin Laden``, I can directly go into the file that has biggest number of lines displayed.

**Example 2**
I run``grep -c --count "defense" technical/911report/*.txt``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep -c --count "defense" technical/911report/*.txt
technical/911report/chapter-1.txt:8
technical/911report/chapter-10.txt:3
technical/911report/chapter-11.txt:6
technical/911report/chapter-12.txt:7
technical/911report/chapter-13.1.txt:14
technical/911report/chapter-13.2.txt:0
technical/911report/chapter-13.3.txt:3
technical/911report/chapter-13.4.txt:2
technical/911report/chapter-13.5.txt:8
technical/911report/chapter-2.txt:1
technical/911report/chapter-3.txt:21
technical/911report/chapter-5.txt:0
technical/911report/chapter-6.txt:11
technical/911report/chapter-7.txt:0
technical/911report/chapter-8.txt:3
technical/911report/chapter-9.txt:2
technical/911report/preface.txt:0
</code></pre>
 I want to see how many lines in each documment containing the word ``defense``. If I want to research more about ``defense``, I can directly go into the file that has biggest number of lines displayed.
 
 
### Option4
``grep -L --files-without-match``

**Example1**
``grep -L --files-without-match "defense" technical/911report/*.txt``
``-L --files-without-match`` displays the file names that does not contains the input string.
<pre><code>
 (base) nicholaslyu@your-ex docsearch % grep -L --files-without-match "defense" technical/911report/*.txt 
technical/911report/chapter-13.2.txt
technical/911report/chapter-5.txt
technical/911report/chapter-7.txt
technical/911report/preface.txt
</code></pre>
I want to see which files in the 911reports folder do not have ``defense`` in them. The output shows those files that do not contain the word ``defense`` as expected. 

**Example2**
``grep -L --files-without-match "media" technical/911report/*.txt``
<pre><code>
(base) nicholaslyu@your-ex docsearch % grep -L --files-without-match "media" technical/911report/*.txt
technical/911report/preface.txt
</code></pre>
I want to see which files in the 911reports folder do not have ``media`` in them. The output shows those files that do not contain the word ``media`` as expected. 


## Reference
All references I used was from ``$man grep`` command.





