<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Quick App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .app-container {
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            width: 320px;
            text-align: center;
        }
        input {
            width: 70%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 6px;
            margin-right: 5px;
        }
        button {
            padding: 10px 15px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
        }
        button:hover {
            background-color: #0056b3;
        }
        ul {
            list-style-type: none;
            padding: 0;
            margin-top: 20px;
        }
        li {
            background: #eee;
            margin: 8px 0;
            padding: 10px;
            border-radius: 6px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .delete-btn {
            background-color: #FF4136;
            padding: 5px 10px;
        }
        .delete-btn:hover {
            background-color: #c0392b;
        }
    </style>
</head>
<body>

    <div class="app-container">
        <h2>✅ My To-Do list</h2>
        <div>
            <input type="text" id="taskInput" placeholder="Enter a task...">
            <button onclick="addTask()">Add</button>
        </div>
        <ul id="taskList"></ul>
    </div>

    <script>
        // This is the brain of the app
        function addTask() {
            let input = document.getElementById("taskInput");
            let taskText = input.value.trim();
            
            if (taskText === "") {
                alert("Please enter a task!");
                return;
            }

            // Create a new list item
            let li = document.createElement("li");
            li.innerHTML = `${taskText} <button class="delete-btn" onclick="this.parentElement.remove()">X</button>`;
            
            // Add it to the list and clear the input box
            document.getElementById("taskList").appendChild(li);
            input.value = "";
        }
    </script>

</body>
</html>
