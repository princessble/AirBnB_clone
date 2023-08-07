# AirBnB_clone

0x00 AirBnB Clone - The Console
AirBnB Clone

Welcome to 0x00 AirBnB Clone - The Console repository! 🏠✨ 

This project is an exciting group endeavor where we build the foundation of our very own AirBnB clone. The console serves as the first step towards creating a complete web application.

Project Description:

In this repository, we'll be creating a command-line interface (CLI) for managing AirBnB objects. This CLI will help us handle various tasks related to our AirBnB clone project. By completing this first step, we'll set the stage for the subsequent projects that involve HTML/CSS templating, database storage, API integration, and front-end development.

Command Interpreter:

The command interpreter is a pivotal part of our project. It empowers us to interact with our AirBnB objects through the command line. To get started, follow these steps:

Clone the repository to your local machine.
Navigate to the project directory.
Launch the console by running ./console.py.

Usage:

Our command interpreter offers a variety of commands to manage AirBnB objects. Some of the available commands include:

create: Creates a new instance of a specified class.
show: Displays the details of a specific object.
all: Lists all instances of a class or all classes.
update: Updates the attributes of an object.
destroy: Deletes a specified object.
To see the full list of available commands and their usage, you can type help within the console.

Examples
Here are a few examples to help you get started:

To create a new instance of User class: create User
To display details of a specific object: show User 12345
To list all instances of a class: all User
To update the attributes of an object: update User 12345 email "newemail@example.com"
To delete an object: destroy User 12345

Authors:

We greatly value collaborative efforts! The individuals who have contributed to this repository are listed in the AUTHORS file. If you're part of the team and your name is missing, please feel free to update the file.

Unit Tests:

Testing is an integral part of our development process. We've incorporated unit tests to ensure the functionality and reliability of our code. All files, classes, and functions have been rigorously tested.

BaseModel Class:

The BaseModel class lays the foundation for other classes in our project. It defines common attributes and methods that will be inherited by other classes. Here's a glimpse of the BaseModel class:

Public Instance Attributes
id: A unique identifier assigned to each instance.
created_at: The datetime when an instance is created.
updated_at: The datetime when an instance is last updated.
Public Instance Methods
save(): Updates the updated_at attribute with the current datetime.
to_dict(): Returns a dictionary containing all attributes of the instance. This method also converts created_at and updated_at to string objects in ISO format.
This class is fundamental to our serialization and deserialization process, as it provides a dictionary representation of our objects.

Create BaseModel from Dictionary:

We've enhanced our BaseModel class to support conversion from a dictionary representation back to an instance. The flow of serialization-deserialization is now as follows:

<class 'BaseModel'> -> to_dict() -> <class 'dict'> -> <class 'BaseModel'>

To achieve this, update the models/base_model.py file:

Implement the __init__(self, *args, **kwargs) method to allow reconstruction from the dictionary representation.
If kwargs is not empty, create attributes based on the keys and values of the dictionary. Remember to handle datetime conversions for created_at and updated_at.
If kwargs is empty, create id and created_at as before.

Store First Object:

Now we can recreate a BaseModel from another one using a dictionary representation:

<class 'BaseModel'> -> to_dict() -> <class 'dict'> -> <class 'BaseModel'>

To make this persistent, we'll save these objects to a JSON file using the FileStorage class. This class serializes instances to a JSON file and deserializes JSON files to instances. Update models/engine/file_storage.py:

Use __file_path and __objects as private class attributes to manage the JSON file and objects.
Implement all(self), new(self, obj), save(self), and reload(self) public instance methods.
Additionally, update models/__init__.py to create a unique FileStorage instance for your application.

Console 0.0.1
We've also developed a program called console.py that contains the entry point of the command interpreter. This command interpreter is implemented using the cmd module. Here's what you need to know:

Class definition: class HBNBCommand(cmd.Cmd)
The interpreter includes commands for quitting, help, and custom prompts.
An empty line followed by ENTER won't execute any command.
The code is not executed when imported.

Remember, the key to success lies in your hands! Let's embark on this exciting journey of building our AirBnB clone. Feel free to explore, contribute, and enjoy the process. If you have any questions or need assistance, don't hesitate to reach out. Happy coding! 🚀🏡✨
