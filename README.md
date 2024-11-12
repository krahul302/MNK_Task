import json
import os

# Task class
class Task:
    def __init__(self, id, title, completed=False):
        self.id = id
        self.title = title
        self.completed = completed

    def __repr__(self):
        status = "Completed" if self.completed else "Not Completed"
        return f"[{self.id}] {self.title} - {status}"

# Task Manager class for handling tasks
class TaskManager:
    def __init__(self):
        self.tasks = []
        self.load_tasks()

    # Add a new task
    def add_task(self, title):
        new_id = self.tasks[-1].id + 1 if self.tasks else 1
        new_task = Task(new_id, title)
        self.tasks.append(new_task)
        print(f"Task '{title}' added.")

    # View all tasks
    def view_tasks(self):
        if not self.tasks:
            print("No tasks available.")
            return
        for task in self.tasks:
            print(task)

    # Delete a task by ID
    def delete_task(self, task_id):
        self.tasks = [task for task in self.tasks if task.id != task_id]
        print(f"Task {task_id} deleted.")

    # Mark a task as complete
    def complete_task(self, task_id):
        for task in self.tasks:
            if task.id == task_id:
                task.completed = True
                print(f"Task {task_id} marked as completed.")
                return
        print(f"No task found with ID {task_id}.")

    # Save tasks to a JSON file
    def save_tasks(self):
        with open("tasks.json", "w") as f:
            json.dump([task.__dict__ for task in self.tasks], f)
        print("Tasks saved to tasks.json.")

    # Load tasks from a JSON file
    def load_tasks(self):
        if os.path.exists("tasks.json"):
            with open("tasks.json", "r") as f:
                tasks_data = json.load(f)
                self.tasks = [Task(**task_data) for task_data in tasks_data]
            print("Tasks loaded from tasks.json.")

# CLI Interface
def main():
    task_manager = TaskManager()
    
    while True:
        print("\nTask Manager CLI")
        print("1. Add Task")
        print("2. View Tasks")
        print("3. Delete Task")
        print("4. Complete Task")
        print("5. Save & Exit")

        choice = input("Choose an option: ")
        
        if choice == "1":
            title = input("Enter task title: ")
            task_manager.add_task(title)
        elif choice == "2":
            task_manager.view_tasks()
        elif choice == "3":
            task_id = int(input("Enter task ID to delete: "))
            task_manager.delete_task(task_id)
        elif choice == "4":
            task_id = int(input("Enter task ID to complete: "))
            task_manager.complete_task(task_id)
        elif choice == "5":
            task_manager.save_tasks()
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()


