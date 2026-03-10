# Ex03 To-Do List using JavaScript
## name:mohan.m
## reg no :212224220064
## Date: 10/03/2026

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
## HTML
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>

<div class="container">
    <h1>TO-DO LIST</h1>

    <div class="input-container">
        <input type="text" id="taskInput" placeholder="Enter your task">
        <button id="addTaskBtn">ADD</button>
    </div>

    <ul id="taskList">
        <!-- Tasks will appear here -->
    </ul>
</div>

<script src="script.js"></script>

</body>
</html>
```

## CSS
```
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

/* Main container */
.container {
    background-color: white;
    padding: 20px;
    width: 400px;
    border: 2px solid #333;
    box-shadow: 5px 5px 10px rgba(0,0,0,0.2);
    text-align: center;
}

/* Title */
h1 {
    margin-bottom: 20px;
}

/* Input section */
.input-container {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
}

/* Input box */
#taskInput {
    flex: 1;
    padding: 10px;
    border: 2px solid #333;
}

/* Add button */
#addTaskBtn {
    padding: 10px 15px;
    background-color: #ff6b6b;
    color: white;
    border: none;
    cursor: pointer;
}

/* Task list */
ul {
    list-style-type: none;
    padding: 0;
}

/* Task item */
li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    border: 1px solid #ccc;
    margin-bottom: 10px;
}

/* Completed task */
.completed {
    text-decoration: line-through;
    color: gray;
}

/* Delete button */
.delete-btn {
    background-color: red;
    color: white;
    border: none;
    padding: 5px 8px;
    cursor: pointer;
}

```

## JS
```

document.addEventListener("DOMContentLoaded", function () {

    const taskInput = document.getElementById("taskInput");
    const addTaskBtn = document.getElementById("addTaskBtn");
    const taskList = document.getElementById("taskList");

    // Add task
    addTaskBtn.addEventListener("click", addTask);

    function addTask() {
        let taskText = taskInput.value.trim();

        if (taskText === "") {
            alert("Please enter a task");
            return;
        }

        // Create list item
        let li = document.createElement("li");

        // Task text
        let span = document.createElement("span");
        span.textContent = taskText;

        // Checkbox
        let checkbox = document.createElement("input");
        checkbox.type = "checkbox";

        checkbox.addEventListener("change", function () {
            span.classList.toggle("completed");
        });

        // Delete button
        let deleteBtn = document.createElement("button");
        deleteBtn.textContent = "Delete";
        deleteBtn.classList.add("delete-btn");

        deleteBtn.addEventListener("click", function () {
            taskList.removeChild(li);
        });

        li.appendChild(checkbox);
        li.appendChild(span);
        li.appendChild(deleteBtn);

        taskList.appendChild(li);

        taskInput.value = "";
    }

    // Add task using Enter key
    taskInput.addEventListener("keypress", function (e) {
        if (e.key === "Enter") {
            addTask();
        }
    });

});
```

## OUTPUT

<img width="1337" height="722" alt="image" src="https://github.com/user-attachments/assets/6aa13ef3-be92-473e-a459-a46279741da8" />



## RESULT
The program for creating To-do list using JavaScript is executed successfully.
