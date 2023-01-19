This material is copyright Simon Dobnik and made available under the Creative Commons Attribution 4.0 International License (CC-BY-SA) license http://creativecommons.org/licenses/by-sa/4.0/
 
Email: simon.dobnik@gu.se
Web: http://dobnik.net/simon/teaching/shared/LT2112-formling/



====== Writing phrase structure grammars ======

In this assignment you will write phrase structure rules to analyse (or parse) some English sentences.

The rules are stored in a grammar file with an extension .fcfg. This is a text file which you can open in a text editor such as TextMate or Emacs. For more information have to write rules have a look at the file example-grammar.fcfg as well as Chapter 8 of the NLTK book (sections 8.1 - 8.3) which you can find here http://www.nltk.org/book/ch08.html

The sentences that your grammar (in grammar.fcfg) should parse are given in a file sentences.txt. Your task is to extend or modify the rules in example-grammar.fcfg so that they will parse sentences.txt in a way that follows our linguistic intuitions. Remember what I said in the lecture: first identify heads and then determine whether there are any modifier phrases which are parts of the the same constituent.

You can run the code by typing the following into a terminal:

$ python parser3

(This depends on what is selected as the default python on your computer. The code requires Python 3 and a recent NLTK. On my computer I have to run "python3.4 parser3" to select Python 3.).

The programme prints out bracketed analyses of sentences and draws their trees graphically. By default it uses example-grammar.txt and example-grammar.fcfg. To start with your grammar and the assignment sentences please uncomment/comment the appropriate lines at the top of parser3.py. Also, if you are doing a quick testing of the grammar you may want to disable drawing of the trees, which you can do by commenting and uncommenting appropriate lines.

Here is an example output:

2:  every cat chases a dog in the garden

(S[]
  (NP[] (Det[] every) (N[] cat))
  (VP[]
    (VP[] (V[] chases) (NP[] (Det[] a) (N[] dog)))
    (PP[] (P[] in) (NP[] (Det[] the) (N[] garden)))))


(S[]
  (NP[] (Det[] every) (N[] cat))
  (VP[]
    (V[] chases)
    (NP[]
      (NP[] (Det[] a) (N[] dog))
      (PP[] (P[] in) (NP[] (Det[] the) (N[] garden))))))


The sentence is syntactically ambiguous as there are two parses depending on the attachment of the prepositional phrase (the number of parses is printed to the left of the sentence). The round brackets () tell is about the constituent structure. There are also square brackets [] which have no use here but we will talk about them in our next lecture.

The assignment is a part of a larger assignment that will be marked at the end of the lecture series. During each lecture we will add more sentences and hence your grammar will become more and more sophisticated. Therefore, it is important that you try to finish each part before we continue with the next lecture. You can also use this opportunity to ask questions. As always you are encouraged to discuss this assignment with your colleagues and me but when it comes down to writing the rules, you have to do this on your own.

Happy grammar writing!

simon.dobnik@gu.se
