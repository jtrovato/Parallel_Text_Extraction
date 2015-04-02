Introduction
============

As shown in class, it is useful for many purposes to have a vast bank of parallel sentences in different langauges. One potentially cheap way to obtain a vast number of such sentence pairs is to harvest them from Wikipedia.

Consider, for example, the English-language Wikipedia article about the United States. It contains the following sentence:

> "Mainstream American cuisine is similar to that in other Western Coutnries."

THe Spanish-language version of the same article contains this sentence:

> "La gastronomía de Estados Unidos es similar a la de otros países occidentales."

Unfortunately, whole WIkipedia articles themselves cannot necessarily be treated as parallel documents because on Wikipedia, not all (and in fact very few) articles are generated by blindly translating from the same article in a different language.

However, as the example about shows, articles often contain sentences that are quite similar. We wnat to identify such pairs of parallel sentences and harvest htem for future use. A human can read through the English and Spanish versions of an article and pick out the pairs of similar sentences. **Your challenge is to write a program that identifies pairs of parallel sentences automatically.**

Given the text of two Wikipedia articles (the first in English and the second in Spanish) with one sentence per line, You should output two parallel files (the first in English and the second in Spanish) containing only the parallel sentences that you identified from the articles. The *i*th sentence in your Spanish document for all *i* from 1 to the length of your output files.


Getting Started
===============

To begin, download the starter kit. In the downloaded directory, you now have `default.py` that <does whatever>/ Test it out using this command: <>

Description of Objective function:
----------------------------------
The underlying task of alignment must be graded with respect to hand aligned data. Because we require the true "labels" we must split the data into a testing and training set. This ensures that results are not being evaluated on the data used to train the algorithms. This separation is standard in machine learning applications. With a sufficient test set, alignment performance can be determined forma  few simple statistics taken on the results.

F1 Score is used to evaluate the performance of our alignment algorithm because it includes information about both the precision and recall of the data. Precision is the percentage of aligned sentences that are correctly aligned, while recall is the percentage of given sentences that are correctly aligned. Both are necessary to gain an idea of performance. For instance, if we only align one sentence and it is correct we would have 100% accuracy. Using the F1 Score makes sure that both precision and accuracy are considered when evaluating.

$$\text{F1 Score}=\frac{2\cdot P(h,e)\cdot R(h,e)}{P(h,e)+R(h,e)}$$

where $P$ and $R$ are precision and recall, defined as:

$$R(h,e)=\frac{\mid h \cap e\mid}{\mid e\mid}$$ and $$P(h,e)=\frac{\mid h \cap e\mid}{\mid h \mid}$$

The data you are given are pre-parsed sentences and headers from parallel Wikipedia articles in English and Spanish. The data comes in the form of pairs of files, labeled <name>.enu.snt for the parsed English sentences and <name>.esn.snt for the parsed Spanish sentences. Each sentence is on a separate line. There is no guarantee that there are equal numbers of sentences in the English and Spanish files.

Your program will take in a pair of such files and find the likely sentence alignments. Your program should create two files in the current directory, one for English output and one for Spanish output, and output these filenames to standard output so the grade program can then locate oyur files. Within these files, you should write only the sentences which your program determines are aligned. Make sure that aligned sentences are at the same line number in the two output files. Your English and Spanish output files should have the same number of lines.

The Challenge
=============

Here are some ideas:

* Create new features such as positional
* Derive features from the [Wikipedia Markup](http://en.wikipedia.org/wiki/Help:Wiki_markup) files provided.
* Develop a [context dependent probability model](http://www.aclweb.org/anthology/I05-1053).
* Build a [maximum entropy](http://www.aclweb.org/anthology/C12-3035) model for parallel sentence alignment.