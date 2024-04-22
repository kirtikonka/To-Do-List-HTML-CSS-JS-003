# JS CODE 

**Event Listener on Add Button:**

* Attaches a click event listener to the element with the ID "push" (presumably a button).
* When the button is clicked, the following happens:

  **Empty Task Check:**
  * Checks if the input field within the element with the ID "newtask" (presumably the input area for adding tasks) has any value.
    * If the value length is 0 (empty), an alert message prompts the user to enter a task.

  **Adding a Task:** (If there's input)
  * Creates a string containing HTML code for a new task element wrapped in a `<div>` with the class "task".
    * The string uses template literals (` `) to embed dynamic content.
    * It includes a `<span>` with the ID "taskname" containing the actual task text entered by the user (using `document.querySelector('#newtask input').value`).
    * It also includes a button element with the class "delete" that likely displays a delete icon using Font Awesome (`<i class="fa-solid fa-delete-left"></i>`).

  * Appends the constructed HTML string to the inner HTML of the element with the ID "tasks" (presumably the list container). This effectively adds the new task to the list.

  **Adding Delete Functionality:**
  * Selects all elements with the class "delete" which represent the delete buttons for tasks (using `querySelectorAll`).
  * Loops through each delete button (`current_tasks`):
      * Attaches a click event listener to each button.
      * When a delete button is clicked, it removes its parent element (the `<div>` containing the entire task) from the DOM using `this.parentNode.remove()`.

  **Adding Mark as Completed Functionality:**
  * Selects all elements with the class "task" which represent the individual task entries (using `querySelectorAll`).
  * Loops through each task element (`tasks`):
      * Attaches a click event listener to each task.
      * When a task is clicked, it toggles the class "completed" on itself using `this.classList.toggle('completed')`. This likely adds a styling effect (like strikethrough) to visually represent a completed task.

  **Clearing the Input Field:**
  * Clears the value of the input field within the element with the ID "newtask" after adding a task.
