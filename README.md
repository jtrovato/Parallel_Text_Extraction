Introduction
============

As shown in class, it is useful for many purposes to have a vast bank of parallel sentences in different langauges. One cheap way to obtain a vast number of such sentence pairs is to harvest them from Wikipedia.

Consider the English-language Wikipedia article about the United States. It contains the following sentence:

> "Mainstream American cuisine is similar to that in other Western Coutnries."

THe Spanish-language version of the same article contains this sentence:

> "La gastronomía de Estados Unidos es similar a la de otros países occidentales."

These two sentences are quite similar, so we want to identify them as a pair. A human can read through the English and Spanish versions of an article


Getting Started
===============

To begin, download the starter kit. In the downloaded directory, you know have <> that <does whatever>/ Test it out using this command: <>

Description of Objective function:
----------------------------------
The underlying task of alignment must be graded with respect to hand aligned data. Because we require the true "labels" we must split the data into a testing and training set. This ensures that results are not being evaluated on the data used to train the algorithms. This separation is standard in machine learning applications. With a sufficient test set, alignment performance can be determined forma  few simple statistics taken on the results.

FScore is used to evaluate the performance of our alignment algorithm because it includes information about both the precision and recall of the data. Precision is the percentage of aligned sentences that are correctly aligned, while recall is the percentage of given sentences that are correctly aligned. Both are necessary to gain an idea of performance. For instance, if we only align one sentence and it is correct we would have 100% accuracy.

The data you are given are pre-parsed sentences and headers from parallel Wikipedia articles in English and Spanish. The data comes in the form of pairs of files, labeled <name>.enu.snt for the parsed English sentences and <name>.esn.snt for the parsed Spanish sentences. Each sentence is on a separate line. There is no guarantee that there are equal numbers of sentences in the English and Spanish files.

Your program will take in a pair of such files and find the likely sentence alignments. Your program should create two files in the current directory, one for English output and one for Spanish output, and output these filenames to standard output so the grade program can then locate oyur files. Within these files, you should write only the sentences which your program determines are aligned. Make sure that aligned sentences are at the same line number in the two output files. Your English and Spanish output files should have the same number of lines.

The Challenge
=============

Here are some ideas:

     * Create new features such as positional
     * Derive features from the [Wikipedia Markup](http://en.wikipedia.org/wiki/Help:Wiki_markup) files provided.
     * Develop a [context dependent probability model](http://www.google.com/url?q=http%3A%2F%2Fwww.aclweb.org%2Fanthology%2FI05-1053&sa=D&sntz=1&usg=AFQjCNEFk7Dm9XlWTlyTsUy1ZWIn9s1NLw).