# To Do List App

This is the "Hello World" of web applications. The reason that it is so 
valuable is because it allows people to understand how the flow of data
works throughout the application, from the user interacting with the frontend
and how it communicates to the backend. Your job today will be implementing
the deliverables to practice all that you have learned.

### Setting Up Your Backend
Through the tool of `json-server` you will be able to use the `todos.json` 
file as your backend. In order to make that happen, you will want to run
the following commands:

```
  $ npm install -g json-server # only if you haven't installed it already
  $ json-server todos.json --watch
```

Your terminal should show you all available routes through the `/todos` resource.

### Deliverables
The following deliverables will be written in terms of user stories. Sentences that are
written in such a way to describe the functionality a user will be able to perform.

- A user will be able to see a list of todos they have to perform. This will display
the title of the todo and whether it is completed or not using a checkbox input.
- A user will be able to create a new todo through a form and it will show in the list
of todos. **When we create a todo, we want to make sure to tell it that it is initially
not complete.**
- A user should be able to update a todo to be completed or not completed. 
**This should NOT create a new todo.**


### HTML Structure
Take a look within the `index.html` provided for you. You will notice that there is already
a given form which we'd like for you to use for creating a new todo, and a div where we'd like
for you to place all todos. Please use the provided spaces appropriately.

If you want a template for your todo, you can use this as an example:

```html
<li>My todo title <input type="checkbox"/></li>
```

### API Documentation
Below you can see some of the requests you can utilize for the above deliverables. This follows
RESTful conventions.

#### Listing all the todos

```
#=> Example Request
GET http://localhost:3000/todos

#=> Example Response
[
  {
    "id": 1,
    "title": "Completing the code Challenge",
    "completed": false
  }
]
```

#### Creating a new Todo

```
#=> Example Request
POST http://localhost:3000/todos

# Required Headers 
{
  "Content-Type": "application/json"
}

# Example Body
{
  "title": "Thank Prince for his help",
  "completed": false
}


#=> Example Response
{
  "title": "Thank Prince for his help",
  "completed": false,
  "id": 2
}
```

#### Updating a todo
To keep it simple, we only want to send in the changes we want to perform.
We will only send whether it is completed or not.

```
#=> Example Request
PATCH http://localhost:3000/todos/:id

# Required Headers 
{
  "Content-Type": "application/json"
}

# Example Body
{
  "completed": true
}


#=> Example Response
{
  "title": "Thank Prince for his help",
  "completed": true,
  "id": 2
}
```