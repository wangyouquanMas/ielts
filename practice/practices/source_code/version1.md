This is a practice lesson .I will give you guys an very specific demo , which is golang channel , this is the core feature of golang,  to help you understand how to read the source code effeciently and effectively. 

So in the beginning , We have to have a question in mind. What you want to know about channel ? Do you have any questions ?    If you do, that’s good. We can move on to our next stage . But if you don’t you have to find a question first .  If you cannot imagine one, it’s okay. You can ask chatgpt to generate one.  

**[open chatgpt]**  

Let’s say , What are the core features of golang Channel ?  

[gpt responses]

Okay ，Now, we got serveral core features about it .   

**[2/8]**

But you should know that , the answer we got is a complete response. which means it includes everything what Ai thinks is imporant .  Should we go look at each of them ? Of course not, we only need to focus on the most important feature.  our resource is limited, we have to put it in the right place.  so I want to introudce a classic pricinple 20/80 principle, which means you spend 20% of your time ,you can get 80% of the outcomes.     So same here. We only need to care about the most important feature . Now Let’s optimize our question: 

What’s the most important feature do you think among the above features ?  

Okay. Now there are only one : which is the goroutine pause and resume. 

**[Don’t fool yourself]**

Now ,Let’s look at this feature. we need to understand the defintion or the meaning of it. 

Because our goal is to understand these features deeper by reading the source code. 

So, If you don’t understand the meaning of this feature ,it’s like a floating boat without destination. 

So ask your self, Do i understand this feature ? There  are only to answers 。 No I don’t  or Yes ,I do. 
For the first, go solve this problem 

**[Example]**

For an abstract concept, the most straightforwad way to understand it is to create a demo.  from abstract to concrete. 

Ask Ai to create a mvp [most basic and related demo]

Okay ,Now , Let’s do it. 

We can use cursor or chatgpt all fine .Now we get the demo. 

Let’s run the demo and test it.  Now Okay, We know what this feature means . 

It will block the gorotuine ,when the channel is full, it will resume it , when the channel is not full. 

Now our question become more specific. 

**[Assumption/Hypotheosis]**

Don’t rush to check the source code now. view it as a journey. It’s more fun to test it by yourself first and compare your thinking process with the source code. You will benefit more from this process. 

Now, ask yourself, if I need to design this pause and resume feature , what will I Do? 

**[Simplify the question]**

If it’s still too hard for you. Go simplify it. Let’s say, let you design a feature ,what would you do first ?

All features are implemented by data structure and algorithm. Right? So we can think about it from this perspective. 

We need to pause the goroutine and resume it later. 

So we need a datasture to store this goroutine.  there are so many options: array, list ,stack, queue …

queue sounds reaonsable .  so we will take queue as a try to temporaray store the gorutine .

Okay, the data structure is established. What about the algorithm. 

The logic is : If the channel is full, we put the current goroutine in queue. If the channel has space later, we awake the goroutine, put it back , make it runnable right .

Yes , That sound actionalbe. right ? 

But there are still some questions : 

1. who controls the gorutine to do this [pause/resume] ? 
2. what happens to the task sent by the gourtine , when the goroutine is puased ? 
3. what happens to the task, when the goroutine is awake ? 
4. when the gorutine sends the value to the channel , do we need lock?

and so on… there are so many follow up questions ,if you keep inquiring .

Now we can say that , it’s time to read the source code. Because Now we alreay have so many valuable questions realated to our goal.  And all these questions will make you on the right tack towards your goal. The answer to each question will reveal the mog ,approach closer to your goal. 

**[Source code : question + cursor + demo (unit test) + ….]**

**[It’s not enought]**

What design you found impressive , you cannot think  about this way? 

can you apply this into your daily work ? 

**[summary]**

Reading the source code is Just like memory a new phrase , new expression in a specific context. The context makes this expression meaningful, the more phrase or new expressions you know, the more you can become articulate .  so as source code.  The mindset or design principles or algorithms you learned in the source code expand you imagination,  expand your tool box. Making you more confident in dealing with barriers.