Task Manager CLI Application
Project Title: Task Manager CLI Application
Description
The Task Manager CLI Application is a simple command-line tool for managing tasks. Users can add new tasks, view all tasks, delete tasks by ID, mark tasks as complete, and save/load tasks to/from a file (tasks.json). This project is designed to give users a quick and convenient way to manage to-do lists directly from the terminal.
Expected Deliverables
•	A command-line application for managing tasks (task_manager.py).
•	A README.md file with usage instructions.
•	A tasks.json file for saving tasks (automatically created upon saving tasks).
Instructions on Running the Application
1.	Clone the Repository Ensure you are in the desired directory and clone the repository.
bash
Copy code
git clone <repository-url>
2.	Navigate to the Project Directory
bash
Copy code
cd task_manager
3.	Run the Application Use the following command to start the application:
bash
Copy code
python task_manager.py
Functionalities Implemented
1.	Add Task
Allows users to add a new task with a title.
2.	View Tasks
Displays all tasks with their ID, title, and completion status.
3.	Delete Task
Removes a task by its ID.
4.	Complete Task
Marks a specified task as completed.
5.	Save & Load Tasks
o	Save: Stores all current tasks in a tasks.json file.
o	Load: Automatically loads tasks from tasks.json on startup (if the file exists).
Usage Example
Upon running the application, you’ll see a menu with options:
markdown
Copy code
Task Manager CLI
1. Add Task
2. View Tasks
3. Delete Task
4. Complete Task
5. Save & Exit
Choose an option:
Choose the corresponding option number to add, view, delete, complete, or save tasks.
________________________________________
This README.md provides all necessary information for a user to understand, run, and utilize the application effectively. Let me know if you'd like further customization!

