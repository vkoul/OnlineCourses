## Computation thinking- Univ of Michigan


### Computational Thinking Overview
- Problem solving approaches for computers to use to solve problems
- Computers are now ubiquotous, they are used to solve our problems
- In order for computers to help us, we need to tell them - we do this using programming
- Computer program is a set of instuctions to solve problems- We can do it in many languages like `Python`, `C`
- Although programming is not the first step, we need to develop a conceptual approach to solve the problem 
- Computational thinking is essentially the blueprint to solve a problem 
	- Is the problem solvable by the computer
	- Can we break the problems into sub-problems
	- Can we see familar patterns/ characteristics
	- Can we identify non essential aspects which we can ignore

### Computational Thinking Mental Models

The four mental models are :
	- **Problem Identification**
	- **Decomposition**
	- **Pattern Recoginition**
	- **Abstraction**

-  Subjective problems like, "what is the funniest movie?". These kind of problems are not solved by computers

- In problem identification, we work on :
	- Topic: What is the big problem which we are working on to solve
	- Data: What is the data which we require to solve the problem
	- Feasibility: Can you solve the problem with current information? Is the problem solveable with a computer

- Problem Decomposition: 
	- Can we break the big problem into sub-problems?
	- Tree charts and flow charts can help us do this well
	- Solving the sub-problems will help us solve the big problem

- Pattern Recoginition
	- Can we think of familiar patterns or characteristics which can help us solve the problems?
	- How are the sub-problems similar or dis-similar to the other problems which you have solved? 

- Abstraction 
	- Identify and ignore the non-essential parts of our problems which we can ignore
	- Are some parts essential to solve the problems or we can get rid of it
	- Worrying too much about the non-essential companents would lead to doing too much at the expense of a successful problem solving

#### Example of computational thinking

**Baking a cake for Grandmother's Birthday Party**

- This is a very high level overview of the problem, so we would need some clarifying answers to get more clarity on this. Some questions can help like:
	- What kind of cake does she like?
	- Does she have an allergy to anything?
	- Any decorations on the cake?
	- How many folks are coming?
	- When is the party (time-deadline)?

- There are multiple sub-problems, for which we need to develop the conceptual solutions:
	- Cake Algorithm
	- Frosting Algorithm
	- Presentation Algorithm
	- Transportation Algorithm
- After breaking down the whole process in the above steps, we need to write the corresponding program for the computer to act on it
- The whole problem solving could be linear in process or it can also be parallel in nature
- Sometimes, you need to solve the sub-problems in some order and sometimes, the order of solving the sub problems doesn't matter

## Week 2:  Case Study: Airport Surveillance and Image Analysis

* Surveliance has 24*7 videos and we need to identify suspicious behaviour from the videos
* How to identify the potential threat from a massive set of videos?
* Important Questions : 
	* What is supicious behaviour? 
	* How to identify it? 
	* How do you quantify it?
	* How to tell a computer to identify the supicious behaviour for us?
* Ques: Why is this a good problem for computers to solve?
	* Coz videos are series of images and images are essentially numbers for computers and it can analyse the numbers at scale which humans can't? 

###  Image Analysis : Abstraction and Algos
* Main question is to abstract this information and put it in an algorithm
* We would like to be able to do:
	* Seprate background to detect movement
	* Identify packages and people
	* Track packages and people
* UMich Prof's have developed an alogorithm called `GRASTA` which is able to separate background from moving objects in real time
	* `GRASTA` : Grassmanian Robust Adaptive Subspace Tracking Algorithm
* How can we identify objects and people : Artifical Intelligence and specifically ML within that
* Essentially, we need to have an algorithm to check suspicious behaviour for every frame:
	* Are there any objects which are not moving?
	* If yes, are they accompanied by a person,
	* if no, then how long have they been there? If it's too much to raise an alarm 
* How we followed the principles of computation thinking in this case study : 
	* **decompose** it into sub-problems. Some of these sub-problems include: separating background and foreground images to detect movement, identifying packages and people, and tracking packages and people.
	* To help solve these sub-problems, we engaged in **pattern recognition** by recognizing that unattended packages should qualify as "suspicious behavior."
	* In the **abstraction** phase, we began to identify what information was relevant to our problem, and what information could be ignored. For instance, we can ignore some stationary objects and background posters, but we can't ignore packages and people. 
### Evaluate Algorithms
* Break down the tasks and check for the individually 
* Combine elements into simple tests: Use short videos with low resolutions
* One can't identify all the edge cases, but we should be able to identify as many cases as possible

### Computation Thinking - II
* In the first iteration of this problem, we **decomposed** it into sub-problems. Some of these sub-problems included: separating background and foreground images to detect movement, identifying packages and people, and tracking packages and people. 
* In the second iteration of this problem, we **decomposed** our problem again by asking "how long is too long for a package to left alone?"
* To help solve these sub-problems, we engaged in **pattern recognition**. In the second iteration, we needed to determine how long is "too long" for a package to be left alone. By looking back at previous surveillance videos, we could establish a normal amount of time for people to leave their luggage.
* In the **abstraction** phase of iteration one, we identified what information was relevant to our problem, and what information could be ignored.

## [Week 3:  Case Study: Introduction to Epidemiology](https://www.coursera.org/learn/compthinking/exam/u6i6Z/airport-surveillance-case-study-quiz)

- The major challenges in Public health are:
	- Is there a new epidemic or pandemic coming?
	- Best way to prevent people from getting sick?
	- Promote healthy habits in people for ex. how to cut down smoking?


## Problem Identification

#### Background
- millions of people are affected every year by flu
- Globally 10% of adults and 20-30% of children get affected by flu
- most of them are mild, however few of the cases can get complicated
- Every year the virus is slightly related to the old one causing seasonal flu or a totally new one causing a **pandemic**

#### Problem Preparation 
- how can we prevent as many infections as possible?
- how to treat those who get affected?
- how to minimise the health and economic costs of flu?

#### Problem Solving
Tools we have:
- Flu vaccine
- Antivirals
- Other prevention strategies: social distancing, handwashing etc

#### Computational Thinking usage
- Predict how many cases we can get and how severe those cases would be and set aside resources as per that
- help determine the best prevention strategies in different settings
-  Who should get priortized in resources are limited?
- In all the above cases, we have algorithms helping us out

#### Abstraction and Decomposition

Building a model of ** flu transmission** .  Abstracting the pieces

* Would like to predict how many people get infected in a year as a function of how many people are vaccinated before the virus shows up?
* How virus spread in your city/town?
	* Schools/ buses/ subways 
* How do people get infected? Where do they get infected?
* We need to extract the key ingredients from this complex problem, so as to help us understand what is crucial in case of identifying the disease
* How much detail should we have in our model?
	* Depends on time and data we have
*  We can have three sets of people in the population : *Infected* , *Recovered* and *Suspectible* 

```mermaid
graph LR
Suspectible ---> Infected(Infected)
Infected --> Recovered{Recovered}
```

- The suspectible can be affected and infected will be recovered. We need to understand the parameters, how S will become I and how I can become R. This is the workhorse model that we will use. 

 #### Epidemiology: Algorithms and Evaluating Solutions - Part 1
#### Infection --> Recovered
- We have three parameters: S, I and R 
- And then people transform from one state to another
- We will assume that there are a certain percentage of people who recover on a particular day, lets assume it to be 10% 
	- So on any given day, 10% people are recovered. 
- If I = 1000 and r = 10% , then people who will recover will be I * r = 100, people getting recovered everyday
- 
#### Suspectible  --> Infection 
- For an infection to occur, S should meet an I. 
- In the meeting, the probability of getting infected- let's call it p 
- Also, how people will get infected will depend on how many people are in S and how many people are in I
##### Contacts
- We need to model a network - specific movement and interaction of folks meeting. Otherwise, we will have to come up with a way count/estimate all interactions
- Lets also have a parameter : *c*, which is the rate at which people meet each other
- Number of meetings in a day = *c* \* *I*  \* *S*
- Avg. number of infections in a day : p * c * I * S
 


## [Week 4:  Case Study: Human Trafficking]





