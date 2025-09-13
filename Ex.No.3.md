# Ex03 To-Do List using JavaScript
## Date: 13/9/2025

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
.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Todo List</title>
  <link rel="stylesheet" href="3.css">
</head>
<body>
  <div class="todo-container">
    <h1>My To-Do List</h1>
    <div class="input-section">
      <input type="text" id="taskInput" placeholder="Enter a task...">
      <select id="prioritySelect">
        <option value="daily">Daily</option>
        <option value="important">Important</option>
        <option value="urgent">Urgent</option>
      </select>
      <button onclick="addTask()">Add</button>
    </div>

    <h2>Daily Tasks</h2>
    <ul id="dailyList"></ul>

    <h2>Important Tasks</h2>
    <ul id="importantList"></ul>

    <h2>Urgent Tasks</h2>
    <ul id="urgentList"></ul>
  </div>

  <script src="3.js"></script>
</body>
</html>
```
.css
```
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  background-image:  url("3.jpg");
  display: flex;
  justify-content: center;
  align-items: flex-start;
  min-height: 100vh;
  padding: 30px;
  margin: 0;
}

.todo-container {
  background: #fff;
  padding: 25px 30px;
  border-radius: 16px;
  box-shadow: 0 6px 20px rgba(0,0,0,0.15);
  width: 420px;
  animation: fadeIn 0.8s ease-in-out;
}

h1 {
  text-align: center;
  color: #333;
  margin-bottom: 15px;
}

h2 {
  margin-top: 20px;
  color: #444;
  border-bottom: 2px solid #eee;
  padding-bottom: 5px;
}

.input-section {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

input, select, button {
  padding: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 14px;
  outline: none;
}

input:focus, select:focus {
  border-color: #007bff;
  box-shadow: 0 0 6px rgba(0,123,255,0.3);
}

button {
  background: #4e5053;
  color: white;
  cursor: pointer;
  border: none;
  transition: 0.3s;
}

button:hover {
  background: #25303c;
  transform: scale(1.05);
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  background: #f9f9f9;
  margin: 8px 0;
  padding: 10px 12px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  transition: 0.3s;
}

li:hover {
  
  transform: translateX(3px);
}

li.completed {
  text-decoration: line-through;
  color: inherit;   
  background: #f9f9f9;  
  opacity: 0.7;     
}


li.daily { border-left: 6px solid #33673f; }   
li.important { border-left: 6px solid #82591c; } 
li.urgent { border-left: 6px solid #59302e; }     

.task-label {
  flex: 1;
  margin-left: 10px;
  font-size: 15px;
}

li button {
  background: #964B00;
  border: none;
  padding: 6px 10px;
  border-radius: 6px;
  color: white;
  font-size: 13px;
  cursor: pointer;
  transition: 0.3s;
}

li button:hover {
  background: #3b2d2e;
}
```
.js
```
function addTask() {
  const input = document.getElementById("taskInput");
  const priority = document.getElementById("prioritySelect").value;
  const taskText = input.value.trim();

  if (taskText === "") {
    alert("Please enter a task!");
    return;
  }

  const li = document.createElement("li");
  li.classList.add(priority);

  const checkbox = document.createElement("input");
  checkbox.type = "checkbox";
  checkbox.onchange = () => li.classList.toggle("completed");

  const label = document.createElement("span");
  label.textContent = taskText;
  label.classList.add("task-label");

  const delBtn = document.createElement("button");
  delBtn.textContent = "Delete";
  delBtn.onclick = () => li.remove();

  li.appendChild(checkbox);
  li.appendChild(label);
  li.appendChild(delBtn);

  if (priority === "daily") {
    document.getElementById("dailyList").appendChild(li);
  } else if (priority === "important") {
    document.getElementById("importantList").appendChild(li);
  } else {
    document.getElementById("urgentList").appendChild(li);
  }

  input.value = ""; 
}
```

## OUTPUT

<img width="1899" height="873" alt="image" src="https://github.com/user-attachments/assets/b6ef9f5a-275c-44e9-a19b-669b2e4dcdf5" />

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
