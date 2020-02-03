---
layout: schedule
title: Schedule

canvas: 
  assignment_url: 'https://canvas.asu.edu/courses/41575/assignments'
  yellowdig_url: 'https://canvas.asu.edu/courses/41575/assignments/959520'
---
 
<!--- 
New sections start with 2 stars:  ** Section Title
New units start with 3 stars:     *** {Unit Metadata}
-----------------------------start example
** Section-I
*** { @unit = "15th Nov", @title = "Course Overview", @reading, @lecture, @assignment, @foldout }
-----------------------------end example
Unit Metadata is comprised of:
@unit - date or number
@title - unit name
@reading - turn on reading icon
@assignment - turn on lecture icon
@lecture - turn on lecture icon
@foldout - activate unit content (allow foldout)
Submit Buttons - 
  <a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">Submit Lab</a>
  <a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>
-->




** Welcome


*** { @unit = "", @title = "Course Overview",  @foldout   }

<br> 

## Welcome Back!

CPP 527 is the second course in the Foundations of Data Science sequence. This semester extends work done in CPP 526 by introducing programming topics like control structures, loops, and regular expressions that are necessary for building simulations and specialized applications in R. We will also cover the foundations of document design using both GitHub pages (free websites like this one) and customized RMD templates so that you can begin developing custom reporting formats so that enable you to better structure results from analytical projects or automate tasks. 

<br>
<br>



*** { @unit = "", @title = "Getting Help", @assignment, @foldout  }


## Getting Help

Note that the discussion board is hosted by the GitHub issues feature. It is a great forum because:

* You can format code and math using standard markdown syntax. 
* You can cut and paste images directly into the message. 
* You can direction responses using @username mentions. 

Please preview your responses before posting to ensure proper formatting. Note that you format code by placing fences around the code:

````
```
# your code here
lm( y ~ x1 + x2 )
```
````

The fences are three back-ticks. These look like quotation marks, but are actually the character at the top left of your keyboard (if you have a US or European keyboard). 

GitHub does not have a native math rendering language (RMD documents, on the other hand, [support formulas](https://www.calvin.edu/~rpruim/courses/s341/S17/from-class/MathinRmd.html)). So you have two options, type formulas as regular text and use code formatting to make them clear (this option is usually sufficient). Or you can type your formula in a formula editor and copy and paste an image of the nicely-formatted example.  

````
```
y = b0 + b1•X1 + b2•X2 + e

b1 = cov(x,y) / var(x)
```
````

----



<br>
<br>











** Week 1 - Control Structures  

*** { @unit = "", @title = "Unit Overview", @foldout  }


## Description

This section introduces [control structures](https://intellipaat.com/blog/tutorial/r-programming/decision-making-and-loops/) that serves to incorporate decision-making into computer code. It enables things like *if-then* logic to determine what code should be used based upon specified conditions. 


## Learning Objectives

Once you have completed this section you will be able to 
* implement if-else statements 
* use while loops 
* use functions as steps in problem-solving 

## Lab

Your assignment this week will be to design computer code to simulate the steps in the game show Let's Make a Deal. 

<br>
<br>



*** { @unit = "", @title = "Readings", @reading, @foldout  }

<br>
<br>

## Review

Please revisit the following chapter from last semester:

[Functions](http://ds4ps.org/dp4ss-textbook/ch-040-functions.html)


## Assigned Reading

Required:

[Quick Reference on Control Structures](https://intellipaat.com/blog/tutorial/r-programming/decision-making-and-loops/) 

[Control Structures in R](https://bookdown.org/rdpeng/rprogdatascience/control-structures.html)



## Recommended Reading 

This topic builds off of the use of loops and thus is a little more advanced - we will cover it in CPP 528. It would not hurt to preview the topic now, though. 

[Don't Loop - Apply](https://bookdown.org/rdpeng/rprogdatascience/loop-functions.html)

[Simulation](https://bookdown.org/rdpeng/rprogdatascience/simulation.html) 

[Scope](https://bookdown.org/rdpeng/rprogdatascience/scoping-rules-of-r.html)

<br>
<br>




*** { @unit = "", @title = "Psuedo-Code", @lecture, @foldout  }

<br>

## Planning Your Code with Pseudo-Code

Typically as you start a specific task in programming there are two things to consider. 

(1) What are the steps needed to complete the task? 
(2) How do I implement each step? How do I translate them into the appropriate functions and syntax? 

It will save you a huge amount of time if you separate these tasks. First, take a step back from the problem that think about the steps. Write down each step in order. Make some notes about what data is needed from the previous step, and what the return result will be from the current step. 

Think back to the cooking example. If we are going to bake cookies our pseudo-code would look something like this: 

1. Preheat the oven. 
2. In a large bowl, mix butter with the sugars until well-combined. 
3. Stir in vanilla and egg until incorporated. 
4. Addflour, baking soda, and salt.  
5. Stir in chocolate chips. 
6. Bake. 

Note that it lacks many necessary details. How much of each ingredient? What temperature does the oven need to be? How long do we bake for? 

Once we have the big picture down and are comfortable with the process then we can start to fill in these details:


1. Preheat the oven. 
  - Preheat to 375 degrees 
  
2. In a large bowl, mix butter with the sugars until well-combined. 
  - 1/3 cup butter    
  - 1/2 cup sugar    
  - 1/4 cup brown sugar   
  - mix until the consistency of wet sand 
 
Note that in computer programming terms butter, sugar, and brown sugar are the inputs or **arguments** needed for a function. The wet sand mixture is the **return value** of the process. 

In the final step, we will begin to implement code. 

```r
# 1. Preheat the oven. 
#    - preheat to 375 degrees 

preheat_oven <- function( temp=375 )
{
   start_oven( temp )
   return( NULL )
}


# 2. In a large bowl, mix butter with the sugars until well-combined. 
#    - 1/3 cup butter    
#    - 1/2 cup sugar    
#    - 1/4 cup brown sugar   
#    - mix until the consistency of wet sand 

mix_sugar <- function( butter=0.33, sugar=0.5, brown.sugar=0.25 )
{
   sugar.mixture <- mix( butter, sugar, brown.sugar )
   return( sugar.mixture )
}


# 3. Stir in vanilla and egg until incorporated. 
#    - add to sugar mixture 
#    - mix until consistency of jelly 

add_wet_ingredients <- function( sugar=sugar.mixture, eggs=2, vanilla=2 )
{
   # note that the results from the previous step are the inputs into this step
}
```

We are describing here the process of writing pseudo-code. It it the practice of:

1. Breaking an analytical task into discrete steps. 
2. Noting the inputs and logic needed at each step. 
3. Implementing code last. 

Pseudo-code helps you start the process and work incrementally. It is important because the part of your brain that does general problem-solving (creating the basic recipe) is different than the part that drafts specific syntax in a langauge and de-bugs the code. If you jump right into the code it is easy to get lost or derailed.  

More importantly, pseudo-code captures the problem logic, and thus it is independet of any specific computer language. When collaborating on projects one person might generate the system logic, and another might implement. So it is important to practice developing a general overview of your task at hand. 

Here are some helpful examples: 

* [Pseudocode guide](https://www.vikingcodeschool.com/software-engineering-basics/what-is-pseudo-coding)
* [Khan Academy video](https://www.khanacademy.org/computing/computer-programming/programming/good-practices/pt/planning-with-pseudo-code) 


<br>
<br>







*** { @unit = "Due Jan 21th", @title = "Lab 01", @assignment, @foldout  }

<br>

## Lab-01 - Control Structures 

This lab is based upon the famous [Monty Hall Problem](http://www.montyhallproblem.com/). 

Although there was much debate about the correct solution when it was initially introduced there are many concise explanations of the proper solution:

<iframe width="560" height="315" src="https://www.youtube.com/embed/9vRUxbzJZ9Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The Monty Hall Problem is a great example of a mathematical problem that might be hard to solve using a mathematical proof, but it is fairly easy to solve using simulation. Since it is just a game with simple and explicit rules we can build our own virtual version. Then we can compare how outcomes differ when we deploy the two different strategies for selecting doors. 

In Lab 01 we will use control structures to build a virtual version of the game. In Lab 02 we will use simulation to play the game thousands of times so that we can get stable estimates of the payoff of each strategy. 


<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/lab-01-instructions.html">LAB-01 Instructions</a>

## Submit Solutions to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>














** Week 2 - Simulations 


*** { @unit = "", @title = "Unit Overview", @lecture, @foldout }


<br>

## Description

This section introduces loops. We will use them to create simulations. 

## Learning Objectives

Once you have completed this section you will be able to 
* use a loop responsibly in your code 
* select appropriate iterators 
* be mindful of the collector vector needed for the loop 

<br>
<br>


*** { @unit = "", @title = "Readings", @reading, @foldout }

<br>
<br>

## Assigned Reading

Required:

[Building Simulations in R: Mastering Loops](https://ds4ps.org/cpp-527-spr-2020/lectures/p-02-loops.html)

[Creating Animations with Loops](https://ds4ps.org/cpp-527-spr-2020/lectures/Animations.html)

Background reading:

[Why Americans Are So Damn Unhealthy, In 4 Shocking Charts](https://www.buzzfeednews.com/article/peteraldhous/american-health-care)

[Buzzfeed Replication Files](https://github.com/BuzzFeedNews/2017-05-us-health-care)

<br>
<br>




*** { @unit = "FRI Jan 24th", @title = "YellowDig Practice Problems", @assignment, @foldout }

<br>

How can you make interesting animations in R? 

We covered a very basic animation - a random walk - in the lecture notes. 

Start game with $10 in cash and see how long you last. At each step you flip a coin and win a dollar, lose a dollar, or stay the same. How long does the average player survive before going bankrupt? 

```r
cash <- 10  
results <- NULL
count <- 1  
while( cash > 0 )
{
  cash <- cash +   
    sample( c(-1,0,1), size=1 )  
  results[count] <- cash  
  count <- count + 1  
}
```

This is a one-dimensional outcome tracked over time. Physicists have used a similar model to examine particle motion. It is called a Brownian Motion model. It is similar to the betting model above except for each time period the particle moves in two dimensions. 

```r
x <- 0  
y <- 0 
for( i in 1:1000 )
{
  x[i+1] <- x[i] + rnorm(1)
  y[i+1] <- y[i] + rnorm(1)
}
```

![](https://raw.githubusercontent.com/DS4PS/cpp-527-spr-2020/master/lectures/gifs/brownian_motion.gif)

## Questions 

Consider the two following problems. 

(1) How long does the **typical** person take to go bankrupt? If you don't want to do a complicated mathematical proof, you can create a simulation, play the game 10,000 times, then report the average period each game lasted. 

What is the code to make this work? 

(2) Note the trailing tail in the Brownian Motion animation. How would you create that as part of an animation? 

<br>

**Post your ideas or solutions on YellowDig:**

Share your ideas about these problems with your classmates. Or share another animation that you found that uses loops. 

<a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>

<br>
<br>





*** { @unit = "FRI Jan 31st", @title = "Lab 02", @assignment, @foldout }

<br>

Please review the instructions at the end of the lecture notes: 

[Building Simulations in R: Mastering Loops](https://ds4ps.org/cpp-527-spr-2020/lectures/p-02-loops.html)

<br>



<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/lab-02-instructions.html">LAB-02 Instructions</a>

## Submit Solutions to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>










** Week 3 - GitHub Pages



*** { @unit = "", @title = "Unit Overview", @foldout }


<br>

## Customized Reporting

A big part of every analysts job is trying to find ways to distill large volumes of data and information down to meaningful bites of knowledge, often for diverse stakeholder audiences that have varying degrees of technical expertise. For this reason, communication skills are extremely valuable for data scientists. You will constantly be challenged to find the interesting story that emerges from an overwhelming amount of data, and find creative ways to tell the story so that information becomes actionable. 

Although it might not sound as edgy as building a machine learning classifier, the ability to create customized reporting formats and automate various steps of analysis will both make you more efficient and also more effective at communication. 

This lab introduces you to one powerful tool for your toolkit - using GitHub pages to build a website quickly and inexpensively (for free, actually). Then use it to host various components of projects including public-facing reports and RMD documents after rendering. 

For the project component of the course we will use a CV template to learn how the **pagedown** package can be used to create highly-customized report templates:

http://nickstrayer.me/cv/

We will also practice automation by the separation of the design elements of reporting from the data contained in the reports. In this example for a CV, Nick Strayer's positions are stored in a CSV file on GitHub:

https://github.com/nstrayer/cv/blob/master/positions.csv

And they are added to the document templates using some custom functions which filter positions and loop through the list to iteratively build the document. 

## GitHub Pages Set-Up

This week's lab will ask you to configure a GitHub page within a repository on your account. GitHub pages are an amazing resource because (1) they allow you to create an unlimited number of websites related to your projects FOR FREE, and (2) they can be created and maintained using Markdown, which simplifies a lot of the complexity of websites. You will learn to link HTML files generated from R Studio so that you can start sharing analytical projects with external audiences. 

The set-up of a simple GitHub page is fairly straight-forward and can be completed in a few basic steps:

![](https://github.com/DS4PS/cpp-527-spr-2020/blob/master/lectures/images/github-pages-setup.gif?raw=true)

This will give you a barebones website with a landing page you can write using Markdown, and a few templates that you can select from. 

You have access to myriad advanced features on the platform. GitHub pages leverage several powerful web frameworks like Jekyll, Bootstrap, Liquid, and Javascript to make customization of static pages both easy and powerful. We will spend some time talking about how the pieces of a website fit together so that you have a rudimentary knowledge of the platform:

[Barebones Jekyll Example](http://ds4ps.org/barebones-jekyll/index)

More importantly, GitHub pages can help demonstrate the concept of page templates. We can design the layout of a graphic, table, or section of text on a page then dynamically populate it with data. GitHub pages allow you to do with with basic HTML and Liquid tags:

[Table Template Example](http://ds4ps.org/barebones-jekyll/page2)

And the **pagedown** package in R allows you to develop a variety of templates using similar principles:

[Pagedown Overview](https://slides.yihui.org/2019-rstudio-conf-pagedown.html#1)

Similar to other work we have done in R, we will start by using some working examples then reverse engineer them so you can see how the pieces fit together. You are not expected to master any of these topics in the short time-frame of the semester. The proper benchmark of knowledge is can you take an existing open source project and adapt it as necessary. 

## Cascading Style Sheets

You will not be required to learn web programming languages like HTML and Javascript (though they are super useful if you invest the time). You do, however, need to become familiar with very basic CSS as it is impossible to do customization without it. CSS started as a somewhat modest project but has evolved into a powerful language. R Markdown documents support CSS, which makes them fully customizable. It will also become more important so you begin to develop dashboards or custom interactive Shiny apps, since CSS is the primary means of controlling layouts and other style elements. 

## Required Reading

Skim the following chapters, reading to get a general sense of concepts and the basics of how each might function. You can skip sections that explain the code in detail. I am more concerned that you understand how these basic pieces fit together, and when you hear terms like "responsive" you conceptually know what people are talking about. 

[Introduction to Web Programming](https://internetingishard.com/html-and-css/introduction/)

[Hello CSS](https://internetingishard.com/html-and-css/hello-css/)

[Responsive Design](https://internetingishard.com/html-and-css/responsive-design/)

[Bootstrap (wikipedia entry)](https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework))



<br>
<br>






*** { @unit = "FRI Jan 31st", @title = "YellowDig Practice Problems", @assignment, @foldout }

<br>

<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/challenge-question-02.html">PRACTICE QUESTION</a>

<br>


<a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>

<br>
<br>




*** { @unit = "TUE Feb 11th", @title = "Lab 03", @assignment  }

<br>
<br>

## Lab-03 - Graphics


<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/lab-03-instructions.html">LAB-03 Instructions</a>

## Submit Solutions to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>









** Week 4 - Regular Expressions 



*** { @unit = "", @title = "Unit Overview" }

<br>

<br>
<br>






*** { @unit = "FRI Feb 7th", @title = "YellowDig Practice Problems", @assignment, @foldout  }

<br>

Explain the following unexpected behaviors: 

### When is 5 larger than 10? 

```r
> (1:10) > 5
 [1] FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE
> (1:10) > "5"
 [1] FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE FALSE
```


### Invisible Dogs 

x is a factor cataloging animals in a shelter, recording the type of animal. 

Why can't I count dogs? 

```r
> x  # TYPE OF ANIMAL (FACTOR)
[1] cat   dog   mouse
Levels: cat dog  mouse

> x == "cat" 
[1]  TRUE FALSE FALSE
> x == "dog"
[1] FALSE FALSE FALSE
> x == "mouse" 
[1] FALSE FALSE  TRUE
```


### Average Years of Edu

I have a sample of 10 people and am trying to determine their average level of education. 12= high school degree, 16 = four-year college degree, etc. 

My data is stored as a factor (which it should be since it is a categorical variable. But that makes it hard to calculate averages. 

What is going wrong here? 

```r
grade.levels <- factor( c(12, 16, 12, 7, 7, 5, 6, 5, 9, 10) )

> # want to know average level of 
> # schooling for sample:
> mean( grade.levels )
[1] NA
Warning message:
In mean.default(grade.levels) :
  argument is not numeric or logical: returning NA
> 
> # mean requires a numeric variable
> mean( as.numeric( grade.levels ) )
[1] 3.8
```

<br>


<a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>

<br>
<br>








*** { @unit = "TUE Feb 18th", @title = "Lab 04", @assignment  }


<br>
<br>

## Lab-04 - 


<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/lab-04-instructions.html">LAB-04 Instructions</a>

## Submit Solutions to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>










** Week 5 - Data APIs 


*** { @unit = "", @title = "Unit Overview" }

<br>

<br>
<br>



*** { @unit = "FRI Feb 14th", @title = "YellowDig Practice Problems", @assignment }

<br>
<br>

<a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>

<br>
<br>



*** { @unit = "TUE Feb 18th", @title = "Lab 05", @assignment  }

<br>
<br>



<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/lab-05-instructions.html">LAB-05 Instructions</a>

## Submit Solutions to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>






** Week 6 - Tidy Data 




*** { @unit = "", @title = "Unit Overview" }

<br>


<br>
<br>




*** { @unit = "FRI Feb 21st", @title = "YellowDig Practice Problems", @assignment  }

<br>

<a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>

<br><br>








*** { @unit = "TUE Feb 25th", @title = "Lab 06", @assignment  }

<br>
<br>

## Lab-06 - 

<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/lab-06-instructions.html">LAB-06 Instructions</a>

## Submit Solutions to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>





** Week 7 - Customized Reporting





*** { @unit = "MON Mar 2nd", @title = "Code-Through Assignment", @assignment }

<br>

## Code-Through

Since you are sharing your code-through with your classmates on Yellowdig, it will serve as your discussion topic this week.

Create a new GitHub repository and upload your code-through to generate an active URL for your tutorial that you can share with classmates. 

<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/LABS/code-through-assignment.html">Code-Through Instructions</a>

## Submit to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT CODE-THROUGH</a>

## Post on Yellowdig

<a class="uk-button uk-button-primary" href="{{page.canvas.yellowdig_url}}">YELLOWDIG</a>

<br>
<br>




*** { @unit = "MON Mar 2nd", @title = "Report Template Assignment", @assignment  }

<br>


<a class="uk-button uk-button-default" href="https://ds4ps.org/cpp-527-spr-2020/labs/final-project-instructions.html">Final Project Instructions</a>

## Submit to Canvas:

<a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT DASHBOARD</a>

<br>
<br>











<style> 
body {
   font-family: "Roboto", sans-serif;
}
 
p.italic {
  font-style: italic;
  color: black !important;
}
td {
  text-align: left;
}
td.i {
  text-align: center;
}
iframe {
  align: middle;
}
article {
  padding-left:20%;
}
em {
  color: black !important;
}
</style>

