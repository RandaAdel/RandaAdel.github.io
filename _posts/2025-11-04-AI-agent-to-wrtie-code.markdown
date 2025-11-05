---
layout: post
title:  AI agent to write code with LangChain
date:   2025-11-05 11:05:55 +0300
image:  /assets/images/blog/agent.jpg
author: Randa Ahmed 
tags:   LLMs
---

**I have came across an article recently talking about building agents for different purposes and the one I decided testing is if it is possible to get analysis done on top of a database I already have. For this purpose I used LangChain and Ollama for LLMs**

Assuming I have a database that contains sales revenue, profit, when the sale was made, and other pieces of information about the sale itself. Those sales are done across a long period of time and each one of them has a full date attached to it. As part of the reporting phase it could be asked to get the total revenue done for the sales over a specific month. 

***Normally the code should follow this order:***
  &emsp;1- Check the scheme of the database and determine the columns to be used. 
<br>
  &emsp;2- Extract months from the date column to be able to calculate the revenue per month. 
<br>
  &emsp;3- Construct the SQL query to sum the revenue and have a pair of month revenue array as an output. 
<br>
  &emsp;4- Write python code to use the output from the SQL to plot the needed bar plot. 
<br>
  &emsp;5- Display the plot and exit. 
<br>

> In this trial I aimed for automating those steps so I can use a prompt to describe the end goal and the LLM should construct the logic and the thinking process without any guidance.
 
***The process in this experiment is:***
  &emsp; 1- Constructing the database and describing the table to be used is crucial for the process.
<br>
  &emsp; 2- There are tools supported by LangChain to deal with database connection like 'SQLDatabaseToolkit' and 'PythonREPL' to execute python code. 
<br>
  &emsp; 3- The language model was able to check the existence of the table, think about the right SQL and python code to write the needed logic for the plot. 
<br>
  &emsp; 4- I ended up with this bar plot 
<p style="text-align: center;">
  <img src="/assets/images/sales-llm.jpg" alt="Additional image description">
</p>

when I started with a user_question = "I have Month, Year, and Revenue columns in my_table, and I want to plot a bar chart of Revenue per month for 2023 using Python. Order by month (January to December). Rotate X-labels 45 degrees. Assume my_table exists — no need to check. Run the Python code so I can see the plot, and stop everything after showing the plot."

***Constraints in the experiment:***
  &emsp; 1- The LLM used makes the trial successful or break it and between the ones I used the range starts from small, fast and doesn't manage to handle the complexity of the steps to large, slower, and able to think about the task and perform it correctly. 
<br>
  &emsp; 2- LangChain has a lot of changes which makes many functions depreciated and there is a need to find their replacements before the code works. 
<br>
  &emsp; 3- There is an element of stability to the model being used so sometimes the output ends up changing slightly from one run to another. 
<br>
  &emsp; 4- SQL syntax could be sometimes challenging for the model while constructing the right query. 
<br>
  &emsp; 5- Writing the required python was done correctly for the majority of the trials.

***Conclusions:***
&emsp; 1- From what I tried it seems like the human element is required within the loop and it would be faster to write the code for the analysis based on my previous experience.
<br> 
&emsp; 2- This could be an interesting option for fast business adhoc requests that answer short straight forward questions that is not too complex for the LLM. 
<br>
&emsp; 3- More exploration to be done on what is next.. 

note: The previous results are based on a single agent experiment which handled the full workflow.. 
 