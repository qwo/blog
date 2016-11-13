+++
title = "Glass Memory Assistant"
date = "2014-01-16T00:37:28"
+++

I worked on a Glass memory assistant at a past Hackathon. It ended up not working out well but many companies are going into space. This was put together for an exercise that required responding to how a technology today can fill a gap in technology in the past in a more efficient way.

From a study in 2001 in leveraging personal mobile tech and using [natural language recognition operation](http://www.hpl.hp.com/techreports/2001/HPL-2001-145.pdf.)


1. What is the societal problem the solution aims to solve?

Memory Assistant - Uses a combination of accessible hardware and software to provide
personal mobile assistants for individuals. The study in 2001 cites the case of storing and retrieving information via natural voice cues and leverages the power of a connected data store trained with data. T

/* hey attempt to test in 2011, using their off-the-shelf technology, to build a personal digital  assistant that communicates by speaking and being spoken to, and accepts information expressed in natural, everyday language. */

2. Who is the customer paying for the solution?
Targets mobile market.
Consumers that own mobile connected devices like PDAs and vendors who sell services for these devices.

3. What are the characteristics/capabilities of the solution?
+ Process Natural Speech
+ Form object relations using SQL
+ parts of speech recognition to support adjectives and noun parts analysis but no ability to add new attributes or attributes families


4. What is the price of the solution?
+  No clear cost, development of technology and hardware are clear

5. What did the developer do well in your opinion?
+ Aimed to use consumer available technologies to test
+ Worked on selecting good use cases to demonstrate (the house with items )

6. What did the developer fail to address or consider?
+  The text to speech service
7. What new problems were introduced by the solution?
+  Since our natural language parsing uses a context-free grammar, it might have seemed that a speech recognizer that accepted a CFG language specification would be appropriate. But, of the two we tried, one ran slowly and gave poor results, while the other used the CFG as a 6 yes/no filter after recognition, rather than as the model for guiding recognition.
+ Security concerns
