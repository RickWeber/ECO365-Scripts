# Scripts

## TL;DR

A script is a clear set of instructions we give to the computer so it can do (some of) our work for us. 

For example, instead of manually looking at sales data and coming up with an educated guess at how much to ramp up production for Christmas, you can automate the process allowing you to spend more time on other problems (e.g. ensuring that your predictions are getting more reliable over time).

## Intro

Programming languages are often split into "interpretted" and "compiled" languages (warning: I'm about to over-simplify here). R is an interpretted language which means we can interact with it on the console. You type something in, and the R interpretter converts that into "machine code" (the code your computer actually understands), runs that code, gets the result, and displays it appropriately.

```R
> print("hello world")
[1] "hello world"
> sqrt(1 + 1)
[1] 1.414214
```

With a compiled language, we have to write out the whole program, then another program converts the whole thing into machine code, *then* you can run the program. This way creates faster programs, but it can also be harder to write the source code because you don't get the instant feedback of an interpretted language.

When we write R code, we will usually take full advantage of the console and iteratively build up a script.

### Example

In your job at Schnikey Schneakers you need to help coordinate production in response to fluctuating demand. 

The "simple" but high effort solution is to spend a lot of your time reading spreadsheets and make an educated guess. Then send emails to each of your factory managers: "Hey Susan, I'm *pretty* sure you should get ready for a lot more orders of 'Air Gordons'."

With a bit of effort up front, you can automate this with an R script. You create a simple program that: 
1. Gets the relevant data from the company's databases,
2. creates a model and applies it to the data,
3. then creates some visualizations to show predicted orders (with confidence bars) for each of your product lines, and finally
4. sends an automated email to you and your factory managers.

This has two big advantages. 

First, it's repeatable. The "educated guess" method leaves a lot up to your mental state. Will you make worse decisions when you're sick? What if you get promoted and need to pass this task off to someone new? How do you help them make good predictions without needing access to your hunches and intuition?

Second, it frees up your time to focus on other problems. For example, now that you're getting automated reports sent out, maybe it's time to give even more refined predictions that you wouldn't otherwise have time to make.

It's just a few more lines of code to update your predictions to account for shoe size. You create a new report and find out that only children are wearing 'Air Gordons' so you can cut costs in half by not ordering 
any units in large sizes.

## What are scripts?

## Common Errors and how to prevent them

### Not using 

### Solving a problem in the console and forgetting to integrate it into the script.

I start every `R` script with this line:

```R
rm(list=ls())
```

Every time I run my script, it clears away everything from the console. Why? 
Because I want to make sure my script works even when I'm on vacation. 

Because R coding is an iterative process where we spend a lot of time at the console, it's easy to solve problems in our [workspace](https://replit.com/@RickWeber/ECO365-Workspace#lesson.md) but forget to bring them into the script. 

So you get this automated report system working, but next week your factory managers are getting emails full of garbled error messages. After several hours of debugging you'll eventually find out that your script needs to do some minor transformation to the data which you had done manually while creating the script, but didn't include in the script itself. 

If you include the `rm(list=ls())` line at the top of your script, you won't convince yourself the script works until it actually does! 

### Solving a problem in the console and forgetting how you did it.

It doesn't help you to know your script doesn't work if you don't know how to fix it. And when you're at the edge of your own competence (a common experience when learning a new skill... and a common experience even when you've been coding a long time!) you'll often stumble on a solution, then stumble right past it again.

First off, if you find yourself in that situation, you should stop and assess the situation. Second, you should look at your R history. If you're using R studio, it'll be easy to search through in its own pane. Otherwise, it will be in your working directory in a text file named `.Rhistory`. You might have to exit R before you can access it.

```R
> q()
Save workspace image? [y/n/c]: y
```

Open up that file in your favorite text editor to look over your code. Compare it to what's in the relevant documentation, and you'll get it sorted out eventually! Then make sure to get it into your script!