Sure! Here's the updated README with the correct author information:

# To-Do List Application - README

## Project Overview

The **To-Do List Application** is a simple Java-based program that allows users to manage their tasks. With this application, users can:
- Add new tasks
- Remove tasks
- Mark tasks as completed
- View all tasks, including their status (Completed/Pending)

This application is implemented using basic Java concepts such as arrays, loops, and conditional statements, offering a simple and interactive command-line interface for task management.

## Features
- **Add Task**: Users can add tasks to the to-do list.
- **Remove Task**: Users can remove tasks by selecting a task number.
- **Mark Task as Completed**: Tasks can be marked as completed, changing their status.
- **View Tasks**: Displays a list of all tasks with their current status.
- **Task Status**: Each task displays whether it is **Pending** or **Completed**.
- **Interactive Menu**: Users interact with a menu to choose operations such as adding, removing, or marking tasks as completed.

## Technologies Used
- **Programming Language**: Java
- **Data Structures**: `ArrayList` for storing tasks
- **User Interface**: Command-line interface (CLI)
- **Class Design**: Two primary classes: `Todo` (for individual tasks) and `TodoList` (for managing the task list)

## Installation

### Prerequisites
- Java 8 or later installed on your system.

### Steps to Set Up
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/DeepakPanneerselvam1455/TodoListApplication.git
   ```

2. **Install Java**:
   - Download and install [Java JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) if it's not already installed.

3. **Run the Application**:
   - Open the project folder in your IDE or run the game directly from the terminal.
   - To run the application via terminal:
     ```bash
     javac TodoList.java
     java TodoList
     ```

## Gameplay

Once the system is running, you will see the following menu options:

1. **Add Task**: Add a new task to the to-do list.
2. **Remove Task**: View existing tasks and remove one by selecting its number.
3. **Mark Task as Completed**: Mark a task as completed by selecting it from the list.
4. **View Tasks**: View all tasks and their statuses (Completed or Pending).
5. **Exit**: Exit the application.

### Example Interaction:
```
To-Do List Menu:
1. Add Task
2. Remove Task
3. Mark Task as Completed
4. View Tasks
5. Exit
Choose an option: 1
Enter the task: Buy groceries

To-Do List Menu:
1. Add Task
2. Remove Task
3. Mark Task as Completed
4. View Tasks
5. Exit
Choose an option: 4
1. Buy groceries (Pending)

To-Do List Menu:
1. Add Task
2. Remove Task
3. Mark Task as Completed
4. View Tasks
5. Exit
Choose an option: 3
Enter task number to mark as completed: 1
Task marked as completed.

To-Do List Menu:
1. Add Task
2. Remove Task
3. Mark Task as Completed
4. View Tasks
5. Exit
Choose an option: 4
1. Buy groceries (Completed)
```

## Code Structure

- **Todo.java**: The `Todo` class represents a task with properties such as task description (`task`) and completion status (`isCompleted`).
- **TodoList.java**: The `TodoList` class manages the collection of tasks and provides methods for adding, removing, marking tasks as completed, and displaying all tasks.

### Example of `Todo.java`

```java
class Todo {
    private String task;
    private boolean isCompleted;

    public Todo(String task) {
        this.task = task;
        this.isCompleted = false;
    }

    public String getTask() {
        return task;
    }

    public boolean isCompleted() {
        return isCompleted;
    }

    public void markAsCompleted() {
        this.isCompleted = true;
    }

    @Override
    public String toString() {
        return task + (isCompleted ? " (Completed)" : " (Pending)");
    }
}
```

### Example of `TodoList.java`

```java
public class TodoList {
    private ArrayList<Todo> tasks;

    public TodoList() {
        tasks = new ArrayList<>();
    }

    public void addTask(String task) {
        tasks.add(new Todo(task));
    }

    public void removeTask(int index) {
        if (index >= 0 && index < tasks.size()) {
            tasks.remove(index);
            System.out.println("Task removed.");
        } else {
            System.out.println("Invalid index.");
        }
    }

    public void markTaskAsCompleted(int index) {
        if (index >= 0 && index < tasks.size()) {
            tasks.get(index).markAsCompleted();
            System.out.println("Task marked as completed.");
        } else {
            System.out.println("Invalid index.");
        }
    }

    public void displayTasks() {
        if (tasks.isEmpty()) {
            System.out.println("No tasks in the list.");
            return;
        }
        for (int i = 0; i < tasks.size(); i++) {
            System.out.println(i + 1 + ". " + tasks.get(i));
        }
    }
}
```

## Author

- **Author**: [Deepak P](https://github.com/DeepakPanneerselvam1455)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or contributions, feel free to open an issue or contact the project maintainer.

- **Contact**: [Deepak P](https://github.com/DeepakPanneerselvam1455)
