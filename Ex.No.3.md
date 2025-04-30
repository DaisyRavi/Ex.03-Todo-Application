# Ex03 To-Do List using JavaScript
## Date:

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
### App.js
```
import { useState } from "react";

function App() {
  const [tasks, setTasks] = useState([]);
  const [newTask, setNewTask] = useState("");

  const addTask = () => {
    if (newTask.trim() === "") return;
    setTasks([...tasks, { text: newTask, completed: false }]);
    setNewTask("");
  };

  const toggleComplete = (index) => {
    const updatedTasks = [...tasks];
    updatedTasks[index].completed = !updatedTasks[index].completed;
    setTasks(updatedTasks);
  };

  const deleteTask = (index) => {
    const updatedTasks = tasks.filter((_, i) => i !== index);
    setTasks(updatedTasks);
  };

  return (
    <div className="min-h-screen bg-gray-100 flex flex-col items-center p-6">
      <h1 className="text-3xl font-bold mb-6">📝 My To-Do List</h1>
      <div className="flex gap-2 mb-4">
        <input
          className="border p-2 rounded-md w-64"
          placeholder="Add a new task..."
          value={newTask}
          onChange={(e) => setNewTask(e.target.value)}
        />
        <button
          className="bg-blue-500 text-white px-4 py-2 rounded-md hover:bg-blue-600"
          onClick={addTask}
        >
          Add
        </button>
      </div>

      <ul className="w-full max-w-md">
        {tasks.map((task, index) => (
          <li
            key={index}
            className={`flex justify-between items-center p-2 mb-2 bg-white shadow rounded-md ${
              task.completed ? "line-through text-gray-400" : ""
            }`}
          >
            <span onClick={() => toggleComplete(index)} className="cursor-pointer">
              {task.text}
            </span>
            <button
              className="text-red-500 hover:text-red-700"
              onClick={() => deleteTask(index)}
            >
              ❌
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;

```

## OUTPUT
![alt text](<exp-3/my-todo-app/src/img/Screenshot 2025-04-30 113008.png>)
![alt text](<exp-3/my-todo-app/src/img/Screenshot 2025-04-30 113027.png>)
## RESULT
The program for creating To-do list using JavaScript is executed successfully.