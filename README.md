AirBnB clone - The console - Y4x

![65f4a1dd9c51265f49d0](https://github.com/Y4xx/AirBnB_clone/assets/122239886/083a16cf-c57b-4151-afbc-75c0820e4c19)

## Project Description
This marks the initial phase of the AirBnB clone project, where the backend was crafted and seamlessly integrated with a console application, leveraging Python's cmd module.
Data, represented as Python objects, finds its home in a JSON file, accessible through the aid of Python's json module.

## Description of the Command Interpreter
The command interpreter mirrors the structure of the Bash shell, with a defined set of commands tailored exclusively for the AirBnB website.
Serving as the frontend of the web app, this command-line interpreter facilitates user interaction with the backend, meticulously developed using Python's Object-Oriented Programming (OOP) paradigm.

Key commands include:
- `show`
- `create`
- `update`
- `destroy`
- `count`

Implemented functionalities encompass:
- Creating new objects (e.g., User or Place)
- Retrieving objects from various sources (files, databases, etc.)
- Performing operations on objects (e.g., counting, computing stats)
- Updating attributes of an object
- Destroying an object

## How to Start It
Follow these instructions to set up the project on your local machine (Linux distro) for development and testing purposes.

## Installing
Clone the project repository from GitHub, containing the fundamental shell program and its dependencies.
```bash
git clone https://{token}@github.com/Y4xx/AirBnB_clone.git
```
Upon cloning, a folder named "AirBnB_clone" will be created, housing essential files for the program's operation:
- `/console.py`: The main executable of the project, serving as the command interpreter.
- `models/engine/file_storage.py`: A class responsible for serializing instances to a JSON file and deserializing from JSON.
- `models/__init__.py`: A unique `FileStorage` instance for the application.
- `models/base_model.py`: A class defining all common attributes/methods for other classes.
- `models/user.py`, `models/state.py`, `models/city.py`, `models/amenity.py`, `models/place.py`, `models/review.py`: Classes inheriting from BaseModel.

## How to Use It
The console operates in two modes: Interactive and Non-interactive.

### Interactive Mode
In this mode, the console displays a prompt `(hbnb)`, allowing users to write and execute commands. After running a command, the prompt reappears, waiting for a new command.

```bash
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$
```

### Non-interactive Mode
The shell runs with a piped command input, executing the command as soon as the shell starts. No prompt appears in this mode, and no further input is expected.

```bash
$ echo "help" |./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
```

## Format of Command Input
Commands need to be piped through an echo in Non-interactive mode. In Interactive Mode, commands are entered with a keyboard, recognized upon pressing the enter key (new line). The console attempts to execute the command, displaying an error message if unsuccessful. Exit Interactive Mode using **CTRL + D**, **CTRL + C**, or the commands **quit** or **EOF**.

## Arguments
Most commands support several options or arguments, separated by spaces for Shell recognition.

The recognizable commands by the interpreter are the following:

|Command| Description |
|--|--|
| **quit or EOF** | Exits the program |
| **Usage** | By itself |
| **-----** | **-----** |
| **help** | Provides a text describing how to use a command.  |
| **Usage** | By itself --or-- **help <command\>** |
| **-----** | **-----** |
| **create** | Creates a new instance of a valid `Class`, saves it (to the JSON file) and prints the `id`.  Valid classes are: BaseModel, User, State, City, Amenity, Place, Review. |
| **Usage** | **create <class name\>**|
| **-----** | **-----** |
| **show** | Prints the string representation of an instance based on the class name and `id`  |
| **Usage** | **show <class name\> <id\>** --or-- **<class name\>.show(<id\>)**|
| **-----** | **-----** |
| **destroy** | Deletes an instance based on the class name and `id` (saves the change into a JSON file).  |
| **Usage** | **destroy <class name\> <id\>** --or-- **<class name>.destroy(<id>)** |
| **-----** | **-----** |
| **all** | Prints all string representation of all instances based or not on the class name.  |
| **Usage** | By itself or **all <class name\>** --or-- **<class name\>.all()** |
| **-----** | **-----** |
| **update** | Updates an instance based on the class name and `id` by adding or updating attribute (saves the changes into a JSON file).  |
| **Usage** | **update <class name\> <id\> <attribute name\> "<attribute value\>"** ---or--- **<class name\>.update(<id\>, <attribute name\>, <attribute value\>)** --or-- **<class name\>.update(<id\>, <dictionary representation\>)**|
| **-----** | **-----** |
| **count** | Retrieve the number of instances of a class.  |
| **Usage** | **<class name\>.count()** |
