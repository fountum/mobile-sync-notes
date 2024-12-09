# ACIT 2515 Practice Exam

# Table of Contents
- [ACIT 2515 Practice Exam](#acit-2515-practice-exam)
- [Table of Contents](#table-of-contents)
- [Basics](#basics)
  - [Collections (Lists, Tuples, Sets, Dictionaries)](#collections-lists-tuples-sets-dictionaries)
      - [Aside](#aside)
  - [Virtual Enviroment](#virtual-enviroment)
  - [Modules and Packages](#modules-and-packages)
- [Testing](#testing)
  - [Unit Testing](#unit-testing)
  - [Fixtures](#fixtures)
  - [Patching and Mocks](#patching-and-mocks)
- [Classes and Objects](#classes-and-objects)
  - [Dunder/Magic methods](#dundermagic-methods)
- [Data Persistence](#data-persistence)
  - [CSV](#csv)
- [SQLAlchemy](#sqlalchemy)
  - [Sessions and Statements](#sessions-and-statements)
  - [Tables](#tables)
- [Flask](#flask)
  - [Template scaffolding](#template-scaffolding)


# Basics
What does this print? 
```
result_a = 17 // 3
result_b = result_a % 2
print(result_b)
```  

Spot the mistakes (2) in this code sample:
```
with open('scripture.txt') as text:
    for number in text.readlines():
        print(number / 100)
```
scripture.txt
```
200
500
800
```
---
<details>
  <summary>Answer</summary>

  1. `open()` is missing a 2nd positional paramter: `mode`. `mode` dictate what is going to happen to the file. In this case, we should use mode `'r'` to read the file: 
  ```
  with open('scripture.txt', 'r') as text:
  ```
  2. When reading from a file, the values extracted will always be type string. So `number / 100` is attempting to divide a string by an integer, which is not possible. The solution is to cast `number` to an integer (or float): 
  ```
  print(int(number) / 100)
  ```
</details>
<br>

## Collections (Lists, Tuples, Sets, Dictionaries)
Write code that combines the items of the lists `food` and `veggies` into a single list:  

<details>
  <summary>Answer</summary>

  ```
  food = ['borgar', 'ice creem']
  veggies = ['leek', 'spinach']
  food.extend(veggies)
  print(food) // ['borgar', 'ice creem', 'leek', 'spinach']
  ```
  #### Aside
  If you used `.append`, you would've added a list instead of the items *inside the list*:
  ```
  food.append(veggies) 
  print(food) // ['borgar', 'ice creem', ['leek', 'spinach']]
  ```
---
</details>  
<br>
What is wrong with this code: 

```
my_friends = ()
my_friends.add('Mavis')

for person in my_friends:
    print(person)
```

<details>
  <summary>Click me</summary>

  There could be multiple answer to this:  
  1. `my_friends` is a tuple, and **tuples are immutable**, meaning they can't be modified after they are created.  
  2. The programmer may have been trying to create an **empty set** in the first line. Tuples and sets share the same syntax, so `()` defaults to an empty tuple. To create an empty set, use `my_friends = set()`
---
</details>
<br>
Using the given dictionary, write a function that prints the name and points of users who have less than 200 points:

```
users = {
    'sam': 370,
    'ashley': 200,
    'sue':-100,
    'davie':99,
    'james': 199
}
```
<details>
  <summary>Answer</summary>
  
  There are many ways to answer this question, but here is one using `dict.items():
  ```
  for key, value in users.items():
    if value < 200:
        print(f'{key}: {value}')
  ```
---
</details>
<br>

Write code that does the following to the string `word = arbitrary` will replace every 'r' an exclamation mark
<details>
  <summary>Answer</summary>

  ```
  word = 'arbitrary'
  letters = word.split('r')
  new_word = '!'.join(letters)
  print(new_word) // a!bit!a!y
  ```

</details>
<br>

## Virtual Enviroment
Write the command that sets up a new Python virtual environement.
<details>
  <summary>Answer</summary>
  ```python -m venv venv```
</details>

## Modules and Packages
Fill in the blanks: A ______ is a group of ______ that has an ______ file.
<details>
  <summary>Answer</summary>

  A **package** is a group **modules** that has an **__init__.py** file.
</details>
<br>

What is the purpose of the `if __name__ == "__main__"` conditional?
<details>
  <summary>Answer</summary>

  Used in (but not limited to) modules, this condtion lets you add code to run when the module file is direcly executed. When the module is used an import, code in `if __name__ == "__main__"` is not executed.

</details>
<br>

I have these packages setup in my project:
```
├── constants.py
├── display 
│ ├── __init__.py
│ └── show_map.py 
├── logic 
│ ├── __init__.py
│ ├── computer 
│ │ ├── __init__.py
│ │ └── aimbot.py 
│ │ 
│ ├── game.py 
│ └── win.py
└── main.py
```
I just made a Python script, what do I write to import:
1. The entire package `computer`
2. The module `show_map.py` but aliased to `show`
3. The functions `start` and `check_points` from `game.py`
  
<details>
  <summary>Answer</summary>
  ```
  import logic.computer
  import display.show_map as show
  from logic.game import start, check_points
  ```
</details>
<br>

# Testing

## Unit Testing

How do you install the package we use to create unit tests in the class?
<details>
  <summary>Answer</summary>
  
  ```
  pip install pytest
  ```
</details>
<br>

Which of these files will `pytest` recognize?
```
test_thing.py
TestAnother.py
somethingTest.py
OneLast_test.py
```
<details>
  <summary>Answer</summary>

  Any files that matches the pattern `test_*.py` or `*_test.py` will be ran by `pytest`:
  ```
  test_thing.py
  OneLast_test.py
  ```
</details>
<br>

Inside a test file, which of these functions will be ran as tests?
```
def test_thingy():
  pass

def thing_test():
  pass

class test_something:
  def test_thing(self):
    pass  

class TestSomething:
  def test_thing2(self):
    pass
```
<details>
  <summary>Answer</summary>

  Functions that begin with `test_` will be recognized by `pytest`. If the function is inside a class, the class' name must begin with `Test`:

  ```
  def test_thingy():
    pass

  class TestSomething:
    def test_thing2(self):
      pass
  ```
</details>
<br>

Create a test that checks the function if the function `add()` is correctly adding numbers.
<details>
  <summary>Answer</summary>

  The important parts to remember is:
  1. test functions must begin with `test_`
  2. use `assert` to test a value
  
  ```
  def test_add():
    result = 9+10
    assert result = 19
  ```
</details>
<br>

Write a test that checks if the fucntion `add()` raises a `TypeError` when give the incorrect variable types for parameters.
<details>
  <summary>Answer</summary>

  Use `with pytest.raises(<ERROR>)` to test for exceptions in tests:
  ```
  def test_add_invalid_type():
    with pytest.raises(TypeError):
      result = add(9, '10') 
  ```
</details>
<br>

## Fixtures
What is the purpose a fixture?
<details>
  <summary>Answer</summary>

  When testing a class, you may find creating a new instance of it in every function to test. You can use fixtures to create a single instance of a class to use across every test.

</details>
<br>

Create a fixture for the class `Student` and use it in a test fucntion

<details>
  <summary>Answer</summary>
   
  ```
  import pytest
    
  @pytest.fixture
  def student(): # fixture creation
    student = Student("Mavis")
    return student
  
  def test_student(student): # pass the function name to use the fixture
    assert student.name == "Mavis"
  ```
  
  Key points:
  1. Create fixtures as global scoped functions using `@pytest.fixture`
  2. Use fixtures in a test by passing it as a parameter to the test function
</details>
<br>

## Patching and Mocks
What problem does patch and mocks solve?
<details>
  <summary>Answer</summary>

  Unit tests should only test the functionality of a single class. If a class relies on another class to perform functions, bugs in that other class can cause our tests to fail. To avoid this, patching can be used to manually assign a value to an attribute of an object and mocks can replace the output of function.
</details>
<br>

Write the code that would patch the attribute `gpa` of `Student` to `4.0`
<details>
  <summary>Answer</summary>

  ```
  monkeypatch.setattr(Student, 'gpa', 4.0)
  ```
</details>
<br>

Write a test that uses `patch` with the function `input()` to return "Hello" and "Goodbye".
<details>
  <summary>Answer</summary>

  ```
  @patch('builtins.input', side_effect['Hello', 'Goodbye'])
  def test_example(mock_input):
      result1 = input()
      result2 = input()
      assert result1 == 'Hello'
      assert result2 == 'Goodbye'
  ```

  Key points:
  1. To create a patch, use `@patch` before creating a function
  2. For multiple values, use `side_effect[]`
  3. To mock `input()`, you need to pass `mock_input` to the test fucntion
</details>
<br>

Write a test that uses `patch` with the fucntion `open` to return 'Nice to meet you' and 'See you later'.

<details>
  <summary>Answer</summary>

  ```
  from unittest.mock import mock_open, patch
  FILE_CONTENTS="line1\nline2\nline3\n"
  @patch("builtins.open", new_callable=mock_open, read_data=FILE_CONTENTS)
  def test_open(mock_file):
    with open("my_file.txt", "r") as fp:
      data = [line.strip() for line in fp.readlines()]
      assert data[0] == "line1"
      assert data[1] == "line2"
  ```

</details>

# Classes and Objects
Explain how the following terms:
1. Classes vs. objects/instances
2. Attributes vs. methods vs. state
3. Encapsulation


<details>
  <summary>Answer</summary>

  Classes are a 'blueprint' to create a thing. An object or instance is one 'copy' of a class. You can have many objects that original from one class, but not the other way around.

  Attributes are the variables of class, while methods are the fucntions. The state of an object are the current values of the attributes.

  Encapsulation is when classes are designed with a public interface used to modify private attributes. This gives the coder more control over how their class can be used. For example, instead of modifying an attribute directly, a setter method can be created. This setter method may perform various checks to ensure that the new value is valid.


</details>
<br>

What are the parameters `self` and `cls` used for? What values do you pass to a function to with these parameters?
<details>
  <summary>Answer</summary>

  `self` must be passed to any method that references or modifies an *the current instance of the class*, as in the instance that has called this method. 

  `cls` must be passed to any method that references or modifies *the class itself* 

  `self` and `cls` are implicit parameters, meaning they are automatically passed to the function regardless of if you have passed any values. However, you still need to explicitly write `self` or `cls` as a parameter when creating a method.  
  
</details>
<br>

I made a class called Book:
```
class Book:
  paperback = True

  def __init__(self, title, author):
    self.title = title
    self.author = author
```
What are the instance and class variables I've created?


<details>
  <summary>Answer</summary>

  Instance variable: variables that belong to an instance. Only that instance has that value. The instance variables are `title` and `author`

  Class variable: variables that belong to a class. This means all instances of a class can access that variable. The class variable is `paperback`


</details>
<br>

What does the `@property` decorator do?


<details>
  <summary>Answer</summary>

  `@property` make lets you can call the method it is placed above as if it were an attribute. This helps with encapsulation.

  
</details>
<br>

What are static methods and class methods?


<details>
  <summary>Answer</summary>

  Static methods (`@staticmethod`) is a method that doesn't recieve a reference to a class or instance. 

  Class methods recieve a reference to the class (`cls`)

</details>
<br>

What is the difference between composition and aggregation?

<details>
  <summary>Answer</summary>

  Composition is when a class creates instances of other classes as an attribute, such as a `Hand `class that is creates 5 `Finger` objects.  

  Aggregation is when a class can have another class as an attribute, but doesn't create it itself. An example would be a `Car `that can have a `Driver` object assigned to an attribute.


</details>
<br>

## Dunder/Magic methods
What are dunder methods?

<details>
  <summary>Answer</summary>

  Methods that run with out explicitly being called, such as `__str__` when you print an instance.
 
</details>
<br>

Complete this class so that:
1. Comparison operators `< `, `>=`, and `==`  use the Student's age
2. Printing the student prints their name and grade
3. `len(<student instance>)` returns the number of courses the student has:  

```
class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade

        self.courses = []
```

<details>
  <summary>Answer</summary>

  ```
  # 1
  def __lt__(self, right): # less than
    return self.age > right.age

  def __ge__(self, right): # greater than or equal to
    return self.age <= right.age
  
  def __eq__(self, right): # equal to
    return self.age = right.age

  # 2
  def __str__(self): 
    return f'{self.name}, Grade: {self.grade}

  # 3
  def __len__(self):
    return len(self.courses)
  ```
</details>
<br>

# Data Persistence 
## CSV
Not gonna write a question about CSVs, but make sure you
1. Know how a CSV file if formatted
2. How to use DictReader and DictWriter 

Example:
```
from csv import DictReader, DictWriter

with open('data.csv', 'r', encoding='utf-8') as file:
    reader = DictReader(file)
    for row in reader:
        print(row)


new_student = {
    'name':"jamie",
    'age': "9",
    'grade':"1"
}
fields=['name', 'age', 'grade']

with open('data.csv', 'a', encoding='utf-8', newline='') as file:
    writer = DictWriter(file, fieldnames=fields)
    writer.writerow(new_student)
```

# SQLAlchemy

What is an ORM?

<details>
  <summary>Answer</summary>

  ORM stands for Object Relational Mapping and it aids in converting SQL rows into objects in programming languages.
</details>

## Sessions and Statements
How do I create sessions *from scratch* in SQL Alchemy?
<details>
  <summary>Answer</summary>

  1. Create a sessionmaker inside the database `.py` script (script with db engine)
``` 
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

engine = create_engine('sqlite:///school.db', echo=True)
Session = sessionmaker(bind=engine)
```
  2. Import into other script
  3. Create a session using:
     1. `session = Session()`
     2. `with Session() as session`
</details>
<br>

What is the general steps I have to take to create and execute a statement?

<details>
  <summary>Answer</summary>

  1. Create a session
  2. Create a statement
  3. Execute the statement on the session
     1. `session.execute(statement)`
  4. Use `scalar()` or `scalars()` depending on what you expect to recieve from the statement

</details>
<br>

What are the general steps taken to add or delete rows to a database in SQLAlchemy?
<details>
  <summary>Answer</summary>

  1. Create a session
  2. Create an instance of the model class you want to add to the data base
  3. Add or delete the object to the session
     1. `session.add(object)`
     2. `session.delete(object)`
  4. Commit the session
     1. `session.commit()`

Write a select statement that returns `Student`s who are less than 13 years old.
<details>
  <summary>Answer</summary>

  ```
  from SQLAlchemy import select

  statement = select(Student).where(Student.age < 13)
  ```
</details>
<br>
What is the difference between `scalar()` and `scalars()`?

<details>
  <summary>Answer</summary>

  Both functions are used with select statements to return results of the query. `scalar()` returns only one result, while `scalars()` returns every result.

</details>
<br>

## Tables
When creating a model for tables in a database, what must each model class inherit?

<details>
  <summary>Answer</summary>

  Base class (DeclaritiveBase)

  ```
  from sqlalchemy.orm import DeclaritiveBase

  class Base(DeclarativeBase):
    pass
  ```
</details>
<br>

Write code that established a one-to-many relationship beteween the model classes `Student` and `Grade`
```
class Student(base):
    __tablename__ = 'student'
    id = mapped_column(INTEGER, primary_key=True)
    name = mapped_column(String)

class Grade(base):
    __tablename__ = 'grade'
    id = mapped_column(INTEGER, primary_key=True)  
    value = mapped_column(INTEGER)
```
<details>
  <summary>Answer</summary>

  In `Student`: 
  ```
  grades = relationship(Grade, back_populates='student')
  ```  
  In `Grade`: 
  ```
  studnet_id = mapped_column(INTEGER, ForeignKey('student.id'))
  student = relationship(Student, back_populates='grades')
  ```
  Key points:
  1. you need to import `relationship` and `ForeignKey` from `sqlalchmey.orm`
  2. `relationship` establishes the relaition ship by taking the Model Class and the name of the variable in that class that established the other end of the relationship
</details>
<br>

# Flask

What is `flask`?
<details>
  <summary>Answer</summary>

  Microframework that handles HTTP requests and responses.

</details>
<br>

Where does flask look for HTML files?
<details>
  <summary>Answer</summary>

  `templates` folder in your project directory.
<details>
<br>

Create a route that sends the client the `index.html` page when they connect to `website.com`
<details>
  <summary>Answer</summary>

  ```
  @app.route('/')
  def home():
      return render_template('index.html')
  ```
</details>
<br>

Create a route that takes a book id from the url to display `book_details.html` for a specific book when connecting to `site.com/book/<id>`
<details>
  <summary>Answer</summary>

  ```
  @app.route('/book/<int:book_id>')
  def get_book_details(book_id):
      return render_template('book_details', book_id=book_id)
  ```
</details>
<br>

Create a route that sends a 404 error code.
<details>
  <summary>Answer</summary>

  ```
  @app.route('/not_found')
  def not_found():
      return 'Resource not found', 404
  ```
</details>
<br>

Using `url_for`, create a link to the book details page with the book id `100`.
<details>
  <summary>Answer</summary>

  First positional parameter must be the **function name** of the route.
  ```
  url_for('get_book_details', book_id=100)
  ```

</details>
<br>

## Template scaffolding
What code do you need to write in your "base" template to make it reusable?

<details>
  <summary>Answer</summary>

  ```
  {% block content %}

  {% endblock %}
  ```
</details>
<br>

What code do you write to use a base template in another HTML file?

<details>
  <summary>Answer</summary>

  ```
  {% extends "base.html" %}
  ```
</details>
<br>

How do you use variables from Python scripts in HTML templates?

<details>
  <summary>Answer</summary>

  In the HTML template:
  ```
  {{ variable }}
  # Also
  {{ thing.attribute }}
  {{ thing.function() }}
  {{ function() }}
  ```

  To pass a variable to a template, you need to add parameters to `render_template`:
  ```
  # This is inside a route
  # The parameters after the first one will be passed to the template
  # The variable name in the template will be assigned to 'mavis'
  return render_template('book_details.html', name='mavis')
  ```
</details>
<br>

How do you create a for loop in an HTML template?

<details>
  <summary>Answer</summary>
  ```
  # you can also use variables in this for loop
  {% for n in range %}
    ...
  {% endfor %}

</details>
<br>

# API
What are ReST APIs used for?
<details>
  <summary>Answer</summary>

  Storing, recieving, managing data

</details>
<br>

What ReST API methods did we use for our project and what do they do?

<details>
  <summary>Answer</summary>

  POST: upload something to server
  GET: get a resource from the server
  PUT: update a resource on the server

<details>

How do you implement the POST method in your routes?
<details>
  <summary>Answer</summary>
  
  In the Python script:
  ```
  @app.route('/books/create', methods=['POST'])
  def create_book():
    # this json contains the data from the browser
    json = request.get_json()
  ```

  In an HTML template:
  ```
  <!-- This should match your route -->
  <form action="/api/books" method="post"> 
      <label for="title">Book Title:</label><br>
      <!-- This input will go in the json -->
      <input type="text" id="title" name="title" required="true"><br>
  </form>
  ```
</details>
<br>

