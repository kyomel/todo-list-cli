# Todo CLI Application

This is a simple command-line application for managing a todo list. It allows users to add tasks, list all tasks, and mark tasks as completed.

## Usage

The application supports the following command-line flags:

- `-task`: Add a new task to the todo list.  
  Example: `todo -task "Buy groceries"`

- `-list`: List all tasks in the todo list.  
  Example: `todo -list`

- `-complete`: Mark a task as completed by specifying its index.  
  Example: `todo -complete 1`

- `-del`: Delete a task from the todo list by specifying its index.  
  Example: `todo -del 2`

## Configuration

The todo list is stored in a JSON file. By default, the file is named `.todo.json`, but this can be overridden by setting the `TODO_FILENAME` environment variable.

## Code Structure

### [main](cci:1://file:///Users/kyomel/go/src/golang-educative/interactive/todo/cmd/todo/main.go:13:0-74:1) Function

1. **Flag Parsing**:  
   The application uses the `flag` package to parse command-line arguments.  
   - `task`: Specifies a new task to add.  
   - `list`: Lists all tasks.  
   - `complete`: Marks a task as completed.  
   - `del`: Deletes a task by its index.

2. **Custom Usage Message**:  
   A custom usage message is defined to provide helpful information about the application.

3. **Environment Variable Check**:  
   The application checks for the `TODO_FILENAME` environment variable to determine the name of the todo file.

4. **Todo List Operations**:  
   - **Get**: Reads the todo list from the file.  
   - **List**: Prints all tasks.  
   - **Complete**: Marks a task as completed and saves the updated list.  
   - **Add**: Adds a new task and saves the updated list.  
   - **Delete**: Removes a task from the list and saves the updated list.

5. **Error Handling**:  
   Errors during file operations are printed to `stderr`, and the application exits with a non-zero status code.

### Dependencies

- `todo`: A custom package that implements the todo list functionality.

## Example Workflow

1. Add a task:  
   ```bash
   todo -task "Finish documentation"
   ```

2. List tasks:  
   ```bash
   todo -list
   ```
   
3. Complete a task:  
   ```bash
   todo -complete 1
   ```
   
4. Delete a task:  
   ```bash
   todo -del 2
   ```
   