# Collaborative Document Day 4
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
 
post-workshop survey:
https://www.surveymonkey.com/r/PYZFNWS

## 👩‍🏫👩‍💻🎓 Instructors 

Sven van der Burg, Jens Wehner
 

## 🧑‍🙋 Helpers 

Djura Smits, Alessio Sclocco
 

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call 
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city 

## 🗓️ Agenda 

* 09:00	Welcome
* 09:15	Introduction to Testing in python
* 10:15	Coffee break
* 10:30	Introduction to Testing in python
* 11:00	Modular Code development
* 11:30	Coffee break
* 11:45	Modular Code development
* 12:45	Wrap-up
* 13:00	END
 

## 🧠 Collaborative Notes 


### Software Engineering

Definition of [Software Engineering](https://en.wikipedia.org/wiki/Software_engineering) in Wikipedia.

Very important is the lifespan of your software project: how long do you see it being used?
Also important is how many people do you expect to use or work on your project.

Things to think about for your software projects:
* Version control
* GitHub / GitLab
* Code review
* Testing
* Documentation

Rule of thumb: the longer the lifespan of your code, the more software engineering techniques you should use. Similar for people, the more people use or collaborate on your software, the more software engineering techniques you should use.

### Testing

Definition of [Software Testing](https://en.wikipedia.org/wiki/Software_testing) in Wikipedia.

Write small programs to run parts of your code and verify the output.

* Unit test: the individual units of your software
* Integration test: the integration of the individual units

Tests are important to keep your software working in the future, and quickly notice when soTmething breaks.
They are also useful to give examples on how to use your code.

Same software engineering rules of thumb apply: if your code is very short lived and only used by you, maybe writing tests is overkill.

### Exercise: Testing locally (25min)

Please use https://coderefinery.github.io/testing/pytest/ (everything you need to do is described in this link).

### Exercise: Testing as part of the CI (15min)

Add the following to your github actions workflow file from yesterday. 

```
    - name: Test with pytest
      run: |
        pytest example.py
```


Add these functions to your ``example.py``:
```python=
def add(a, b):
    return a + b


def test_add():
    assert add(2, 3) == 5
    assert add('space', 'ship') == 'spaceship'


def subtract(a, b):
    return a + b  # <--- fix this 


# uncomment the following test
#def test_subtract():
#    assert subtract(2, 3) == -1
```

See what the CI does now and then uncomment the ``test_substract`` test.See what the CI does now, Afterwards fix the ``subtract`` function.

### Exercise 4: Test design (35min)

Write tests for the following functions/classes. Also test the error condition:
```python
#1
def factorial(n):
    """
    Computes the factorial of n.
    """
    if n < 0:
        raise ValueError('received negative input')
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result


# 2
def count_word_occurrence_in_string(text, word):
    """
    Counts how often word appears in text.
    Example: if text is "one two one two three four"
             and word is "one", then this function returns 2
    """
    words = text.split()
    return words.count(word)


# 3
def count_word_occurrence_in_file(file_name, word):
    """
    Counts how often word appears in file file_name.
    Example: if file contains "one two one two three four"
             and word is "one", then this function returns 2
    """
    count = 0
    with open(file_name, 'r') as f:
        for line in f:
            words = line.split()
            count += words.count(word)
    return count


# 4
def check_reactor_temperature(temperature_celsius):
    """
    Checks whether temperature is above max_temperature
    and returns a status.
    """
    from reactor import max_temperature
    if temperature_celsius > max_temperature:
        status = 1
    else:
        status = 0
    return status


# 5
class Pet:
    def __init__(self, name):
        self.name = name
        self.hunger = 0
    def go_for_a_walk(self):  # <-- how would you test this function?
        self.hunger += 1
        
```

[The solutions!](https://coderefinery.github.io/testing/test-design/)

[Using temp path functionality from pytest](https://docs.pytest.org/en/stable/tmpdir.html)

### Modular Code Design

Definition of [Modular Programming](https://en.wikipedia.org/wiki/Modular_programming) in Wikipedia.

#### What is modular code development for you?

* Aafke: code that you could easily reuse in different projects (without the need to rewrite a lot)
* Tareq: separate code for different functions (can be (re-)used for different projects)
* Banafsheh:
* Nele: methodology that is needed in multiple places is in functions that can then be called in those places rather than repeating the code.
* Wietske: My guess is: make code that consists of re-usable parts, so you use it in other projects aswell.
* Judith:
* Michael: short functions (single-purpose), seperate functions in utils and main functions, well scalable.
* Farzam:
* Antonio: Split your code in many functions that carry out small and well-defined operations. Make modules with blocks of your code. Use classes and clear separation between private and public members. Use derived classes and inheritance.
* Nada:
* Akshatha:
* Paul: write functions that only do one thing and have rather many small functions than one big one
* Marieke:
* Justin:
* Eef: small & reusable functions
* Omar: divide your code into blocks of codes
* Siri:
* Felicia:Every function does exactly one thing - and not multiple things. They can then be reused at different places.
* Anne Fleur: I have no idea... using classes? 
* Benito: Separate the code on isolated subparts (modules, classes, etc) so it is easier to handle, updated or test (few changes only affect a small part of code).
* Dario: Divide the code into modules. Have classes that wrap together and call each function in the right order.
* Nicolas: Keep functions short
* Rodrigo:
* Kenzie:
* Shan:
* Bouke: Split the code up in modules/functions, such that you prevent repetitive pieces of code and can reuse the functions
* Jeppe:
* Sandra: functional units. 
* Mark: Writing code in smaller, more abstract units such that they can be re-used for other cases aswell. 
* Martine: Organizing your code in smaller pieces in such a way that is better understandable and reusable
* Bram:
* Dirk-Jan: Write code that can be recycled and reused multiple times

####  What are your best practices to get readable code?

* Aafke: easy to understand names of variables, use spaces and explanatory comments
* Tareq:
* Banafsheh:
* Nele: add comments, clear naming
* Wietske: clear names for functions and variables
* Judith:                                  
* Michael: 
* Farzam:
* Antonio: clear and easy variable names. Comments.
* Nada:
* Akshatha:
* Paul:
* Marieke:
* Justin: one task, one function!
* Eef: use Java. clear naming of variable. comment 
* Omar:
* Siri:
* Felicia:
* Anne Fleur:use clear variable names, add a lot of clarification comments
* Benito:
* Dario: Use proper documentation. Try to keep one flow and don't bounce too much between the modules: input --> Module 1 --> Module 2 --> Module 3 --> output
* Nicolas: clear names and documentation
* Rodrigo:
* Kenzie:
* Shan:
* Bouke:
* Jeppe:
* Sandra: design patterns, one-function-one-task principle (good division of logic)
* Mark:
* Martine: Organize functions in classes. Breaking down large functions into smaller ones
* Bram:
* Dirk-Jan: clear naming, splitting functions if the indentation goes too far

#### Exercise: Collaboratively Improving Code

Type your suggestions in the following list:

* Different name for the picture :heavy_check_mark: 
* Write functions for each task (like calculating the mean of a list of numbers) +2 :heavy_check_mark:
* Create a main function to call these functions. +1 :heavy_check_mark:
* Don't hardcode names +1
* filename and output name as external parameters (either to be passed by command line or in a function call).
* Write some comments! Especially the function docstring. You can also ask Spyder/Pycharm to prepare them for you!
* Avoid global variables
* Import the matplotlib package inside the CreateImage function

## Feedback for today

### Tops (what went well)
* I really liked the exercises where we had to write our own test functions, putting it into practice really helps, and being in the groups to discuss was really nice.
* I enjoyed the testing a lot, with the different examples
* Working on the tests was really fun and looking together at writing modular code was very usefull
* Comprehensive set of topics with good modular exercises. Good pace. Lots of enthusiasm. 
* I really liked the course format, with small group sessions and small practicals in breakout rooms. I learnt a lot, both on how I should do things and on what's the best practice to do things. I think my codes (and, eventually, their users) will benefit from this course!
* I really liked the exercise on writing tests for those 5 functions. Very useful, because I had to look up things myself etc. That helps to remember things. This is something that I will try to use in the future for sure.
* writing test functions was really helpful. also to look at them together afterwards

### Tips (what can be improved)
* Comply to your own rules (e.g. write proper docstrings in your examples on the day after you have discussed documentation)
* I thought it would have been nice to also have such an on-your-own practice for the modular code as we did for the tests.
* I agree with the previoous comment, maybe a short particle on modules (just how to do a module folder, a __init__.py file and how to call a home-made module) could have been nice (not sure how it could fit in the course time, though). 
* Some breakout excercise sessions might have been shorter, especially in this last day, but it might also depend on the level of the people in my breakout rooms. We were all done in a few minutes.
* It would have been nice to have, in the sessions about git conflicts, a real-case scenarion with, e.g., merging the master into a development branch where some changes have been made: how to stash, resolve the conflicts in command line and so on. Maybe very advanced for someone, but very tricky to understand by yourself by just googling around.
* we could have spend a bit more time looking at the test functions together (especially the one testing a class)
## Post-workshop survey:
https://www.surveymonkey.com/r/PYZFNWS


## ❓🤔 Q&A
* Q: How do I get a certificate of attendance?
    * A: Send an email to training@esciencecenter.nl

* Q: For how long will the hackmd documents be available?
    * A: We will archive them (in theory forever, in practice probably for a year) with personally identifiable information removed and send you an email with links of where to find it. Also slides will be shared this way.


## 📚 Resources 
 
 * [What Every Computer Scientist Should Know About Floating-Point Arithmetic](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html)
 * [How should I do floating point comparison?](https://stackoverflow.com/questions/4915462/how-should-i-do-floating-point-comparison)
 * [PyTest Getting Started](https://docs.pytest.org/en/stable/getting-started.html)
 * [Test-driven Development](https://en.wikipedia.org/wiki/Test-driven_development)
 * [eScience center guide on software development](https://guide.esciencecenter.nl/#/)