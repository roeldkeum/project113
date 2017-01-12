#The new block 3 graphs

Last updated: 25th December
Here are the graphs for block 3. Note that these are not the graphs that will be used in the tournament. More about that below.

Download the graphs by following this link!
Note that within the block 1 graphs it sometimes occurred that an edge appeared twice in the list e.g. 20 15 and 15 20. This was unintentional and was caused by the use of a number of third-party graphs which used a slightly different convention to me. Sorry if this caused any headaches. (Of course, from a graph colouring perspective such multi-edges do not impact upon the chromatic number). In the block 3 graphs above and the tournament graphs there will be no such repeated edges -- I have checked.

#The tournament

##Overview

In the tournament I will run your code on 20 graphs that have a similar (but not identical) structure to the block 3 graphs given above. You do not get to see these graphs, but if your code performs well on the block 3 graphs you will almost certainly do well in the tournament.

The same 20 graphs are used for every group.

For each graph I give your code 3 minutes. In this time you need to compute the best lower and upper bounds you can (and, of course, if possible, the true chromatic number). I will automatically kill your code after 3 minutes (using the timeout command). Let LB be the best lower bound output by your code for the graph and let UB be the best upper bound. The penalty that your group obtains for this graph is defined as follows:

min(UB - chromatic number, 10) + min(chromatic number - LB, 10)
The total penalty for your group is obtained by summing the penalties for the 20 graphs. Hence, the best possible outcome is 0, while the worst possible outcome is 20*(10+10) = 400. Note that the min(*,10) is there to avoid the phenomenon where a group is punished disproportionately for performing poorly on just one single graph.

Groups will be ranked according to total penalty. At this point some joker will say: the highest penalty wins, right? Ha ha, that's funny that is.

As mentioned in the project book, the best 3 groups will receive a prize. If there is a tie within the top 3 I will use some special tie-breaker graphs to produce an unambiguous ordering of the top 3.

##The rules - yes you certainly need to read this

Any deviation from these rules will result in automatic disqualification!
You need to submit a version of your code to me as a single executable Jar file. It should have the name GroupX.jar where X is your group number. There is lots of information on the internet about how to create an executable Jar file.
I will run your code on my DKE work computer, which is based on a quad-core 64-bit Intel i5-2400 CPU running at 3.1 GHz. It has 4 Gb memory.
I will run it inside Cygwin (a program which equips Windows with a UNIX-like shell) running under Windows 8.
Your code will be run from the command line like this:
timeout 180 java -jar GroupX.jar [filename of graph]

To capture the output of your code I will redirect the output of the above command to a file which will be processed later. To enable easy processing of the file, I require that your code produces output simply by printing text to the screen (with the System.out.println() command). The following output is allowed. No other output is allowed. You must adhere strictly to this format, including spaces. The number Y should be an integer - do not output fractional or floating point numbers (i.e. numbers like 3.0, 7.52 etc. are not allowed).
NEW BEST UPPER BOUND = Y
NEW BEST LOWER BOUND = Y
CHROMATIC NUMBER = Y
You can print as many of the UPPER BOUND and LOWER BOUND statements as you like, in any order. The most natural thing, of course, is to print an improved bound as soon as you discover it. I will process your output to extract the largest lower bound you output, and the smallest upper bound. (To be completely clear: a lower bound is any integer x such that x is less than or equal to the true chromatic number, and an upper bound is any integer x such that x is greater than or equal to the true chromatic number.)

If your code concludes that you have found the true chromatic number, you can output the CHROMATIC NUMBER statement and simply stop. Alternatively, if you have already output matching upper and lower bounds, I will obviously notice this and conclude that this is the chromatic number (and in that case printing CHROMATIC NUMBER is optional). Note: if you output the CHROMATIC NUMBER statement, it should be the very last thing you output. Do NOT use the CHROMATIC NUMBER statement to output non-optimal upper bounds or guesses!

For the graphs in the tournament dataset I do know the true chromatic numbers, so I will detect if your code outputs incorrect output for a given graph (e.g. an upper bound that is lower than the true optimum...) In that case your penalty for that graph will automatically be the maximum possible: 20. Correct code is important!
Several people have asked if they can use multiple threads in the code. I have thought a lot about this. My answer: yes, you can, because you might find threads useful for managing how you divide the 3 minutes. (If you don't know what threads are: they are a way of executing code concurrently). I will, however, ensure that the spare cores in my computer are very busy with other tasks, so executing multiple threads will not give you an advantage in terms of raw processing power. I do this to prevent that a group gets a factor-4 speed up simply because they have a programmer in the group who knows how to launch code across multiple cores. Also, with problems like chromatic number it's (in my humble opinion) much better trying to spend time improving the inherent algorithmic efficiency of your code, than looking for engineering solutions. It is perfectly possible to win this tournament without using threads.

##Deadlines and results

The deadline for the submission of the tournament code is Tuesday 24th January at 12 noon (i.e. 12 o'clock in the afternoon). This will give me enough time to run the tournament and to analyse the results. Note that this is different to the other deadlines involved in the project -- obviously these other deadlines still apply for the other deliverables.
I will inform you of your group's score (and ranking) at the final project presentations. May the odds be ever in your favour...
