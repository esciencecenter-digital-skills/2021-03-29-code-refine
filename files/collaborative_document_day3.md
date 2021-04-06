# Collaborative Document Day 3
2021-03-29 Code Refinery

Welcome to The Workshop Collaborative Document 
 

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents. 

All content is publicly available under the Creative Commons Attribution License 

https://creativecommons.org/licenses/by/4.0/ 

 ---------------------------------------------------------------------------- 

* Collaborative Document day 1: [link](https://hackmd.io/@svenvanderburg/Byy93ar4_/edit) 
* Collaborative Document day 2: [link](https://hackmd.io/@svenvanderburg/r1xIRTSNd/edit)
* Collaborative Document day 3: [link](https://hackmd.io/@svenvanderburg/r1UF0prVu/edit)
* Collaborative Document day 4: [link](https://hackmd.io/@svenvanderburg/rkocCTHV_/edit)

  

## 👮Code of Conduct 
* Participants are expected to follow those guidelines: 
* Use welcoming and inclusive language 
* Be respectful of different viewpoints and experiences 
* Gracefully accept constructive criticism 
* Focus on what is best for the community 
* Show courtesy and respect towards other community members 
 

## ⚖️ License 

All content is publicly available under the Creative Commons Attribution License: https://creativecommons.org/licenses/by/4.0/ 

 

## 🙋Getting help 
to ask a question, type `/hand` in the chat window 

to get help, type `/help` in the chat window 

you can ask questions in the document or chat window and helpers will try to help you 
 

## 🖥 Workshop website 

https://escience-academy.github.io/2021-03-29-code-refine/


🛠 Setup 
https://escience-academy.github.io/2021-03-29-code-refine/#setup
 

## 👩‍🏫👩‍💻🎓 Instructors 

Sven van der Burg, Jens Wehner
 

## 🧑‍🙋 Helpers 

Djura Smits, Alessio Sclocco
 


## 🗓️ Agenda 

* 09:00	Welcome
* 09:15 Selected question answering from yesterday
* 09:30	Introduction to Continuous Integration
* 10:15	Coffee break
* 10:30	Introduction to Continuous Integration
* 11:00	Documentation
* 11:30	Coffee break
* 11:45	Documentation
* 12:45	Wrap-up
* 13:00	END

### Exercises
### Exercise: Setup Continuous Integration on Github
In this exercise, you will:
- Create a repository on GitHub
- Commit code to the repository and set up linting with GitHub Actions
- *Linting* is the process of checking your code for errors or code style violations.

#### Step 1: Create a new repository on GitHub
- **Before** you create the repository, select **"Initialize this repository
  with a README"** (otherwise you try to clone an empty repo).

#### Step 2: Clone your own repository, add code, commit, and push

Clone the repository.

Add a file `example.py` containing:

```python
def print_temperature():
    print(temperature)
```

Then stage the file (`git add <filename>`), commit (`git commit -m "some commit message"`),
and push the changes (`git push origin main`).


#### Step 3: Enable automated testing

In this step we will enable GitHub Actions.
Select "Actions" from your GitHub repository page. You get to a page
"Get started with GitHub Actions". Select the button for "Set up
this workflow" under Python Application.

GitHub creates the following file for you in the subfolder `.github/workflows`:


   ```yaml
   # This workflow will install Python dependencies, run tests and lint with a single version of Python
   # For more information see: https://help.github.com/actions/language-and-framework-guides/using-python-with-github-actions

   name: Python application

   on:
     push:
       branches: [ main ]
     pull_request:
       branches: [ main ]

   jobs:
     build:

       runs-on: ubuntu-latest

       steps:
       - uses: actions/checkout@v2
       - name: Set up Python 3.8
         uses: actions/setup-python@v2
         with:
           python-version: 3.8
       - name: Install dependencies
         run: |
           python -m pip install --upgrade pip
           pip install flake8 pytest
           if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
       - name: Lint with flake8
         run: |
           # stop the build if there are Python syntax errors or undefined names
           flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
           # exit-zero treats all errors as warnings. The GitHub editor is 127 chars wide
           flake8 . --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
       - name: Test with pytest
         run: |
           pytest
   ```

Remove the last part:
```yaml
   - name: Test with pytest
     run: |
       pytest
```
We will get back to this in the lesson on testing.

Commit the change by pressing the "Start Commit" button.

#### Step 4: Verify that github action has been automatically run

Observe in the repository how the github action fails. While the github action is executing, the repository has a yellow marker.
This is replaced with a red check mark, once it is done.

Also browse the "Actions" tab and look at the steps there and their output.

You should be able to find that the linter complains:
``` F821 undefined name 'temperature'.```

step 4 needs the addition of pulling the linter to your local device, step 5 needs additional pushing to github

#### Step 5: Fix the undefined name error
Indeed we forgot to define a variable `temperature`

Let's fix that:
```python
temperature = 10

def print_temperature():
    print(temperature)
```
Commit this change!  

#### Step 5: Verify that github action runs succesfully
Now that you fixed the bug in your code the github action should succeed.

#### Step 6: Understanding github action yaml syntax
This is the part of the github action yaml configuration that is responsible
for the linting step:
```yaml
    - name: Lint with flake8
      run: |
        # stop the build if there are Python syntax errors or undefined names
        flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
        # exit-zero treats all errors as warnings. The GitHub editor is 127 chars wide
        flake8 . --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
```        
It basically just calls the program `flake8` with some arguments. `flake8` is a python linter.

### Recap continuous integration
#### What questions do you still have?
* Banafsheh 
* Farzam: what is the difference between flake8 and travis for instance? 
* (Anne) Fleur   - asked in breakout room
* Wietske 
* Dirk-Jan  
* Aafke: I was able to ask my questions in the breakout room  
* Felicia  
* Bouke  
* Nicolas 
* Nele: Are there by any chance examples of what the setup would look like for a mixed environment?
* Michael: no questions
* Justin: how to protect branches from faulty commits?  
* Tareq  
* Martine  Can you show us some examples -with different complexity- of continuous integration in software from the escience center?
* Paul: Examples would help indeed. Maybe of some project which resembles a research repo (so with analysis scripts in R/Python) but also markdown etc.
* Eef: -  
* Benito 
* Shan
* Antonio  Does this workflow option also exists in gitlab? and if so, is it configured similarly?
* Judith   So if you want to extend your FLAKE8 test, you download the plugings and it automatically checks with what the plugin does, or do you have to change the python action in github or something like that?
* Mark: How would you implenent this for projects you do by yourself, on (only) your local machine? Far that case, isn't the whole github-actions a bit overkill?
* Dario Marzella
* Sandra: just performing the linting does not seem to be the most useful. Should figure out what else it could do. 


#### Are there any incremental improvements that can benefit your project?
* Banafsheh
* Farzam: the project i'm joining already has linting and travis and testing. So i'm mostly understanding what is going on there
* (Anne) Fleur  
* Wietske 
* Dirk-Jan  
* Aafke: Yes, this is great!
* Felicia  
* Bouke: Yes, I think linting can be implemented without much effort. So why not integrate this double check! 
* Nicolas 
* Nele: I like this idea of double-checking code.
* Michael: It's nice everyone is working with the same style of code. It's also nice that people don't change the style of the whole code, so git diff doesn't go crazy.
* Justin
* Tareq: I think from now on I will try to use linting on my main branch
* Martine: I think especially tomorrow will be very useful. I would really like to include tests that check if my code 'makes sense'
* Paul: setting up github actions seems easy and useful for any project
* Eef  
* Benito 
* Shan 
* Antonio  Not at the moment since I'm developing the code for my project alone. But it's definitely useful for future collaborations.
* Judith   n
* Mark Snelders  
* Dario Marzella
* Sandra: yes, think we should set this up (in java in our case)

#### What did we learn that is overkill for your work?
* Banafsheh
* Farzam: i guess coding conventions can (at least in the beginning) become a bit annoying. 
* (Anne) Fleur  
* Wietske 
* Dirk-Jan  
* Aafke: very useful, no overkill for me (I want to save this link for later, can I paste it here? : https://flake8.pycqa.org/en/latest/)
* Felicia  
* Bouke  
* Nicolas 
* Nele: No overkill, seems useful and simple to do (at least for a purely Python project).
* Michael: Seems to have a lot of freedom to choose what you want to test, so no overkill.
* Justin
* Tareq: linting over every commit seems a bit much.  
* Martine: Coding conventions and modular code are useful for me (so no overkill). The biggest challenge is having the whole team comply
* Paul: no overkill so far
* Eef  
* Benito 
* Shan 
* Antonio  
* Judith   n
* Mark Snelders  
* Dario Marzella nope

### Exercise: Think of good and bad examples 
Write down your thoughts in the collaborative documents.
Respond with emojis :+1: :scream_cat: to your colleagues' answers.
- Think of projects of which you like the documentation. What do you like about them?
- Think of projects for which you don’t like the documentation. What don’t you like about them? Are you missing anything?

**NB: You can choose a mature library with lots of users for this exercise, but try to also think of less mature projects you had to collaborate on, or papers you had to reproduce.**

* Banafsheh: I like documents with lots of examples and explain the details about the code.
* Farzam: I like documentatinos which show the "call stack" as well, so one would understand who is calling who and how! As for bad examples, the current project I am joinig does not have a documentation, so there is that!
* (Anne) Fleur  - I like it when they give many examples of how to run the code (when working from terminal), bad example: def preprocessing(): '''this code preprocesses the data''' --> doesn't tell you anything, bad example: when the format of the input data is not clearly defined (this takes SO long to figure out). I like it when they provide some data that you can use to test run the code (so you know for sure it works in the first place)
* Wietske : I mostly miss examples in documentation, especially when there are many options, if not most/all options are shown it is sometimes hd to use it. 
* Dirk-Jan: I like it when all options are described with examples.
* Aafke: I like it when they explain the rationale behind it, maybe some visuals. I don't like it when there is no real explanation of what the variables mean (what the chosen names stand for)  
* Bouke: I like it when there is a blog with examples to help get started. Bad example from a course where we had to use a library created by the lecturer. There was no documentation, only a brief readme that referred to examples.   
* Nicolas: I remember liking SpaCy's documentation a lot when first using it, simply because it was very easy to navigate - more generally: Cheat sheets, summaries and examples are great. Also clear & detailed installation instructions
* Nele: One very bad example I had was in one of the courses that I took during my Master's at TU Delft. We had to use a software developed by the lecturer for our assignments - it took us weeks to somehow understand the code. It was not clear what functions were doing, and there were also very cryptic error messages. Also no examples or outdated ones that no longer worked.
* Michael: - What I like about some documentations is that they also write down the math/algos/link to papers when they implement some formula or algorithm.  - What I don't like is that people don't clearly write what the type of the arguments are, so you get a lot of errors if you don't use the correct type/class.
* Justin: https://matchms.readthedocs.io/en/latest/ - consistent, structured documentation - you know what to expect  
* Tareq: https://docs.pyvista.org/ (to me an example of good documentation) - elaborate, contains examples, easy to find functions. 
* Paul: I like if there is some overview document explaining the structure of the repository. It's also helpful if variables in a datasets get explained somewhere (rather than just having some semi informative name) 
* Eef : proper naming of variables. Docstrings that explain all variables and the correct outcome of the function. :+1: 
* Benito: good ones when the expected parameterers are well defined (type, values, units in science! many packages with "assumed" units but you don't know clearly which ones) and what it returns.:+1:  Bad examples when someone describes the obvious things that one program/function does. But nothing relevant on I/O. And the classical one: _out-of-date_ documentation that is completely different from the current version.   
* Shan good examples: name the understandable parameters and functions and with minimum necessary comments
* Antonio  Lis the meaning of input / output variables for public functions. And a one-sentence brief explanation of what the function does.
* Sandra: docstrings should explain all input/output in a concise way. A more extensive manual is nice. I guess our own project is a bad example in terms of docstrings; our manual is very informative. The code from my Advanced Bioinformatics students is well-documented (under pressure!).
* Judith    Good examples: explane what the code does, which packages are necessary and comment per section what happens and show a quick example of how to run the code, with for example some basic plots. Bad examples: explain the script but not what the output looks like.
* Mark Snelders: Bad: matplotlib, the documentation is too much and too abstract, almost no easy-to-understand examples. Good: any function with a nice docstring which explains the input values and types, and the output value(s) and types and also gives an short example. 
* Dario Marzella I like when inputs and outputs are clearly explained. I like when the logic of a code block is explained. I don't like when 
* Omar: Optimal level of details within the documentation (not too little) with examples
* Martine: Prerequisites are important; I found out that these are often non existent or not complete, make is difficult to reuse


### Exercise: Writing good comments
Let's take a look at two example comments (comments in python start with `#`):
#### Comment A
```python
# Now we check if temperature is larger then -50:
if temperature > -50:
    print('do something')
```

#### Comment B
```python
# We regard temperatures below -50 degrees as measurement errors
if temperature > -50:
    print('do something')
```
 Which of these comments is best? Can you explain why?
 Write your answer in the collaborative document (before looking at others' answers)
 
* Banafsheh: I prefer B, because it explain it better
* Farzam:
* (Anne) Fleur  I like B better because it provides the rationale for WHY we check the temperature (it gives a bit of context)
* Wietske: Comment B, because it explains why -50 is chosen. Without any context it gives me more context.
* Dirk-Jan: I prefer B if it is clear from the rest of the code what to do with measurement errors; otherwise A.  
* Aafke: I like B better, as it explains why you want to check this  
* Felicia: I prefer B because it is not just describiing what I can plainly see in the code but giving me a reason for why this was implemented  
* Bouke: B, comment A is clear from the code itself. Comment B explains why this code is there.  
* Nicolas: I prefer B because it explains the rationale behind the code 
* Nele: I like the second one better. Tells me why we need to check this, which makes it also easier to change the code if e.g. the definition of measurement error changes. A) is just the if-statement in words.
* Michael: I like the second one better, first one just writes the code down in words. Second one gives an interpretation of the code.
* Justin: B - it provides rationale  
* Tareq: I prefer A, if I want to use it for my own work, but it has no contextual value. 
* Martine: comment in A is obsolete: code speaks for itself
* Paul: the second comment B. A is just repeating in words what the function  already states. Comment B is tackling the question: why do we need this function?
* Eef: B, as it gives an explanation why the if statement is there
* Benito: B.  A comment doesn't provide any additional information. 
* Shan B comment should provide some extra information about the function/variable. A is just psudocode...
* Antonio: Option A is useless as the code self explains that already. Comments should add additional meaning to the code, not repeat it.
* Judith    B, because it explains why temperatures below 50 have to be disgarded
* Mark Snelders: I like B, it shows why the -50 threshold is taken.
* Dario Marzella: B makes much more sense to me
* Omar Comment B seems more conclusive. A is easier to understandomment B seems more conclusive.
* Akshatha : B looks better since it explains the rationale behind the condition. Comment A just states in words the code line condition itself, so no additional info is conveyed
* Sandra: A is less informative and contains a typo
* Siri: I would combine both so you can go quickly through the script and you do not need to read the part of code in detail


### Correct Exercise: Adding in-code documentation

 Update this code snippet so it is well-documented:

 ```python
 import pandas as pd
 

 def x(a, print_columns=False):
    b = pd.read_excel(a)
    column_headers = list(b.columns.values)
    if print_columns:
        print("\n".join(column_headers))
    return column_headers
 ```
 1. Work individually on your solution (5 minutes)
 2. One person screen-shares their solution, discuss and together settle on a final solution. (5 minutes)
 3. Share final solution in collaborative document.


##### Group 1:
```python
"""
    * get_column_headers (we changed the name of the function)
    * also change the variable names: [a: file, b: df]
    Gets the columns headers for excel files
    
    args: 
        a (String): an excel file address, such as local address or url
        print_columns (Boolean, default=False): a flag to print column header. Prints the column headers if True, otherwise skips it
        
    returns:
        also returns the column headers of the excel file as a list
"""
```
##### Group 3 (Anne, Michael, Banafsheh):
 ```python
 import pandas as pd
 
 def print_excel_headers(excel_file, print_columns=False):
     """
     prints the column headers
     
     Args:
         file (.xlsx file): path to Excel file which contains column names
         print_colums (boolean, default = False): True if you want to print the column headers

     Returns:
         column_headers (list): List of column names
     """
    df_read = pd.read_excel(excel_file)
    column_headers = list(df_read.columns.values)
    if print_columns:
        print("\n".join(column_headers))
    return column_headers

    
```
##### Group 6 (Bouke, Aafke, Tareq, Akshatha) 
```python=
import pandas as pd

def give_headers_excel(excelfile, print_columns=False):
    '''
    Prints the headers of the columns of the input excel file
    
    args:
        excelfile: path to the excel file .xls
        print_colums (True/False (default)): 
                False: does not print the headers
                True: prints the headers
    returns:
        column_headers: list
        
    '''
   exceldoc = pd.read_excel(excelfile)
   column_headers = list(exceldoc.columns.values)
   if print_columns:
       print("\n".join(column_headers))
   return column_headers
```
##### Group 4 (Eef, Felicia, Omar, Sandra)
```python=

#!/usr/bin/env python3
"""
Author: Sven, I guess
Date: 31-3-2021
Script to print out the column header of an excel file
"""

# Import statements
import pandas as pd

# Function definitions
def get_column headers(excel_fn, print_columns=False):
    """Return a list of column headers from an excel file
    
    excel_fn: string, path to the input file, expected EXCEL format
    print_columns: bool, if True, the headers are printed to stdout
        (DEFAULT=False)
    """
    table = pd.read_excel(excel_fn)
    column_headers = list(table.columns.values)
    if print_columns:
        print("\n".join(column_headers))
    return column_headers
```

#### Group 5
```python=
import pandas as pd

def x(a, print_columns=False):
   """
   Reads Excel file and returns column headers
   
   Args:
       a (str): Name of the excel file that has to be read
       
       optional:
       print_columns (boolean): default is False, not to print the column headers
       
   Returns:
       (list): Column names in the Excel file
   """
    
   b = pd.read_excel(a)
   column_headers = list(b.columns.values)
   if print_columns:
       print("\n".join(column_headers))
   return column_headers
```

##### Wietske 
##### Dirk-Jan
 
##### Felicia 
##### Bouke
##### Nicolas 
##### Nele
##### Michael 
##### Justin 

##### Martine
##### Paul 
##### Eef
##### Benito 
##### Shan 
##### Antonio
```python
import pandas as pd
 
def get_columns_excelfile(file_name, print_columns=False):
    """
    Get the headers of the columns of the spreadsheet

    Args:
        file_name (str): path to the input excel file
        print_columns (bool): option to print out the extracted headers

    Returns:
        (List[str]) the list of column names of the input file 
    """
    pd_frame = pd.read_excel(file_name)
    column_headers = list(pd_frame.columns.values)
    if print_columns:
        print("\n".join(column_headers))
    return column_headers
```  
##### (Judith, Mark, Dario Marzella, Dirk-Jan)
```python
import pandas as pd

def x(a, print_columns=False):
    ''' Reads an excel file and eventually prints out the labels

    Args:
        a (str): path to the excel file
        print_columns (bool): If true, prints the column headers. Default to False.

    Example:
        >>> x('./myexcel.xls', print_columns=True)

    Returns:
        column_header (list(str)): list of strings, each one is a column header
    '''

    # Read and parse the input file
    b = pd.read_excel(a)
    column_headers = list(b.columns.values)

    # In case print_columns=True, print the headers one by one
    if print_columns:
        print("\n".join(column_headers))

    return column_headers
```
##### Omar
##### Akshatha
##### Sandra
##### Siri


 ### Exercise: Write a README file
 You are going to write a README file for an example project.

 #### The example project
 Here's [the example project](https://github.com/escience-academy/coderefinery-documentation-example-project).
 For this project we transformed the code snippets from the previous episode into a single script [analyse_spreadsheet.py](https://github.com/escience-academy/coderefinery-documentation-example-project/blob/main/analyse_spreadsheet.py)
 
 Let's take a look at [the script](https://github.com/escience-academy/coderefinery-documentation-example-project/blob/main/analyse_spreadsheet.py). 
 You don't need to understand the script completely, all you need to know is:
 * The functions `mean_temperature` and `get_spreadsheet_columns` from previous episode are in there.
 * We added a `main` function that is called when you run the script 
 (you could run this python script by calling `python analyse_spreadsheet.py` on the command line). 
 It will prompt the user for a file name, print the columns in the spreadsheet, and print the mean
 temperature.
 
 That's all there is to this project! (You can ignore the other files in the repository, we'll get back to them in episode 4)

 #### The exercise (20 minutes)
 1. Fork [the example project](https://github.com/escience-academy/coderefinery-documentation-example-project) to your own github namespace
 2. Add a file called `README.md` (you can use the github web interface or work locally (i.e. `git clone`, edit the file,  `git add`, `git commit`, `git push`))
 3. Add some content to your README file. Think about what you want the audience to know about your project! 
    It does not matter whether the information is correct, it is more important that you have all the components that make up a good README file.
 4. Note that the README file is nicely rendered on the github repository page.
 5. Discuss your ideas on a good README file in the breakout room. What should definitely be included? Write down a short list in the collaborative document.

 NB: The `README.md` file is written in 'Markdown' a very popular lightweight markup language, all you need to know for now is this syntax:
 ```
 # A section title
 ## A subsection title
 Normal text
 
 A list with items
 - item1
 - item2
 ```
  
 (Optional): Use [https://hemingwayapp.com/](https://hemingwayapp.com/) to analyse your README file and make your writing bold and clear!
 
 ##### Group 1
- Description: This software analyses temperature data in a spreadsheet
- Get started:
    - Prerequisites:Make sure you have a spreadsheet containing temperature data
    - Install software: Clone this repository and then install dependencies
    - Run: The program will prompt you for the path to the spreadsheet 
- Authors: including contact information
- Contributing
- License
 
 ##### Group 2
 ```
# Example Project
This project is about XY.

## requirement.txt
Which packages are required to run all functions

## docs
...

## analyse_spreadsheet.py
Analyse a spreadsheet file with temperatures

## references
If you use our code, please cite us:
*awesome citation

## license
 ```
 
 ##### Group 3
 https://github.com/MichaelDarmoutomo/coderefinery-documentation-example-project
 
 ##### Group 4
 ##### Group 5
 ##### Group 6
 - About the project
 - Getting started
     - Requirements
     - Installation
- Usage and examples
- License
- Authors
 ```
 
 # Code Refinery Documentation Example

This code is used to learn how to write documentation. The first few sentences should give an overview of what this code is used for. 

## Requirements

This code requires python version X.
A list of required python modules are listed in requirements.txt

## Installation instructions (if any)

Step-by-step guide how to install and configure the software. 
Make it clear how you know it's successful and maybe give a few commonly seen error messages and how to fix them.
Who to contact if you have problems. 

## Specific scripts and what they do

Give a list of scripts in the project and the main purpose.
This is also a good place to give an overview of the directory structure.

- analyse_spreadsheet.py :  contains functions

## How to run and example
python analyse_spreadsheet.py 

Example: 
  

## How to cite
Give here the relevant paper/reference to cite your code
```
 ##### Group 6
 ##### Group 7
 ```
 # coderefinery-documentation-example-project
Example project for coderefinery documentation lesson

## Description
![Alt Text](https://i.stack.imgur.com/7PH4h.png)

This is overview is not from our project, we just stole it from google.

### ./spreadsheet_analyser.py
This is a python script that can analyse your spreadsheets. Specifically, it will analyse a spreadsheet that contains among others the air temperature.

Here you can find a nice example table of easy excercises you can give to a Master Student: 
|Assignment|Skill|Level (from 1 to 10)|
|---|---|---|
|Hello_world.py|Python|1|
|---|---|---|
|---|---|---|
|AlphaFold_3.py|Python, DeepLearning, Omniscience|100|

## Installation
### With pip
This project can **definitely** be installed with
```
pip install coderefinery-documentation-example-project
```
so try this command. It will change your life.

### From source
You can also install this from source by following these steps:
1. Clone the GitHub repo
```
git clone https://github.com/DarioMarzella/coderefinery-documentation-example-project.git
```
2. Move into the repo
```
cd https://github.com/DarioMarzella/coderefinery-documentation-example-project.git
```
3. Don't do absolutely nothing
```
echo 'I am not doing anything!'
```
## Usage
### ./spreadsheet_analyser.py 
#### running example
```
python ./spreadsheet_analyser.py
```

#### logic
The script will perform the following steps:
- Ask for a filename (should be the spreadsheet)
- Print the column headers of each column
- Print the mean temperature of the column called "Air temperature (degC)"



## Crucial conclusion
![Alt Text](https://media.giphy.com/media/vFKqnCdLPNOKc/giphy.gif)

 ```
 
 
 ### Think about what you learned
- What questions do you still have? 
- Whether there are any incremental improvements that can benefit your projects 
- What’s nice that we learnt but is overkill for your current work? 
- What do you know about testing?

* Banafsheh 
* (Anne) Fleur  One more general question that I have is: how do I use git for when I'm not working on one specific project (e.g. loose pieces of code to just do some basic data analysis/plots). I think the instruction on how to structure documentation was very useful, bc I usually do it in a less structured way. I know nothing about testing beyond running code on my computer and seeing if it causes error.
* Wietske Right now no questions. I will start making at least basic documentation, this was a good starting point! For me extensive documentation is now a overkill, but the demo was nice to see. I know testing exists, but I am lost on how to start.
* Dirk-Jan: No questions; nice to see the documentation, but it was a bit much to directly implement. I will need to look at it again if I want to use it; I know about testing in Java, but not in python. 
* Aafke: Especially the information and practice on the README file was useful for me.(and the combination of docstrings with the overview page was new to me and very interesting, but slight overkill for me right now) I know only a bit about testing (mostly theoretical, not a lot of practice yet).  
* Bouke: I Think the best practices on the README files will be usefull. Think so far, the sphynx part is overkill but it might be usefull later. No experience with testing.  
* Nicolas: Useful best practices for documentation that will help future me and collaborators; tensions between simplicity and detail when creating readme's. I had a quik ook at unit testing once - that's about it
* Nele: Looks useful. Now I have no excuses anymore not to create proper docstrings and readmes. Different types of testing. I once did an internship with automating UI-testing, for example. I have also heard of unit tests, but I don't use those myself. I have also heard of unit tests, but I don't use those myself. I have also heard of unit tests, but I don't use those myself. I have also heard of unit tests, but I don't use those myself. I have also heard of unit tests, but I don't use those myself. I have also heard of unit tests, but I don't use those myself. 
* Michael: I will try to use docstrings more from now on. Some of my codes are just scripts, I guess it would be overkill to create a docs file for it. CI is very useful for double checking and making everyones code align.
* Justin: how all the in-code and other types of documentatio work togeter. Testing is becoming much more popular and used within eScience projects that I work on and it would be useful to know the basic phylosophy and structure behind them  
* Tareq: How to properly use docstrings and an interesting (but short) introduction to Sphinx and readthedocs   
* Martine
* Paul: I have a better idea of how to structure README files and if I need more extensive documentation I will look in to Sphinx. One question (but that is maybe too context dependent) is how to structure a repository in general (like folder structure etc.). Are there guidelines/best practice 
* Eef: No questions. I really liked the linting exercise. Making docstrings was an overkill for me. 
* Benito: Useful overview on documentation. Readthedocs+sphinxs is simething to look at now. 
* Shan: I really like the documentation part. I will start to use what Ive learnt today immediately.
* Antonio: I know about unit testing but I don't know how to set it up in python + github. I will definitely implement the linting option in my projects. I definitely think documentation is important but in my current position (PhD student) this is far from being a priority, unfortunately.
* Judith   no more questions: very helpful to organize my documentation more, so I can understand my own code later on. I don't know about testing yet.
* Mark Snelders: The usage of docstrings was really nice, good to know how powerful they can be in combination with readthedocs+Sphinx. I have little experience with testing. What to do when a test fails and it is not your code/repo? 
* Dario Marzella: 
* Omar
* Akshatha
* Sandra
* Siri

### Feedback for today
#### Tops (what went well?):
* I enjoyed working in a small group on the exercises 
* I liked discussing the improved code with others, because they thought differently about what is clear for others than I did.
* Documentation was presented a motivating as it can be.
* I liked the demo on setting up the CI workflow in github.
* Great discussions on various aspects of documentation
* I enjoyed working in the breakout room and the help I received there. It was very useful to learn about the use of the flake8 workflow.
* I liked the part on linking, seems very useful. Structure/planning was good today as well!
* I enjoyed today, useful insight into CD/CI
* I liked the exercises. It gives you a better understanding faster. Maybe sometimes we had to wait a bit, but that was OK.
* It was clear when the breaks happened
#### Tips (what can be improved?):
* Sphinx seems very useful. I would have loved to spend more time on it, but I understand that it can be overkill for some of the participants.
* I would have liked to spend more time addressing options of CI workflows: difference between python package and application. Different options to run flake8 (like checking for naming conventions / more advanced things)
* I found the exercises for the comment / documentation part today not very useful. It would have been nice an exercise on how to set up the doc with Sphinx.
* More info/practice with Sphinx would have been great!
* More info/practice with flake8 (options, good-practice, warnings, errors) would have been great. You could spend less time on the README.md exercise. Just showing the key essentials of a README.md and a cheat-sheet with the formatting would have been enough. :+1:
* an example with readthedocs would've been very useful indeed.
### Command Log

```python=
def mean_temperature(data):
    temperatures = data['Air temperature (degC))']
    return sum(temperatures)/len(temperatures)
```

Including docstring:
```python=
```python=
def mean_temperature(data):
    """
    Get the mean temperature
    
    Args:
        data (pandas.DataFrame): A pandas dataframe with air temperatures measurements.
        
    Returns:
        The mean air temperature (float)
    """
    temperatures = data['Air temperature (degC))']
    return sum(temperatures)/len(temperatures)
```

Retrieving documentation of function:
```python
help(mean_temperature)
```



## 📚 Resources 
* [Git Flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
* [Pycharm resolve conflicts](https://www.jetbrains.com/help/pycharm/resolve-conflicts.html)
* [Google style python docstrings](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)
* [Getting started with Sphinx](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html)
* [GitHub Gists](https://gist.github.com/)