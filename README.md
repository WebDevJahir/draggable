# Project: Draggable Board Project

## Overview

This project is designed to create a draggable board that contains multiple predefined items, allowing users to move these items freely within the board. The implementation is built using vue.js without the use of any third-party libraries, adhering to industrial best practices for clean, maintainable code, and ensuring an intuitive user interface.

## Approach

### 1. **Understanding Requirements**

The project requirements specified the need for a board that could contain movable items, maintaining their positions through state management. Key requirements included:
- A defined number of items with initial positions.
- Functionality to drag and drop items.
- No reliance on third-party libraries to keep the implementation straightforward.

### 2. **Setting Up the Project**

The initial step involved setting up a Vue.js project using a suitable boilerplate (e.g., Create Vue App). This setup provides a foundational structure for organizing components, styles, and assets.

### 2. **Run the Project**

To run the project, follow these steps:
- Unzip the project folder.
- Open the terminal and navigate to the project directory.
- Run the following command to install dependencies:
  ```
  npm install
  ```
- Run the following command to start the application:
  ```
    npm run dev
    ```
- Open a browser and navigate to `http://localhost:5173/` to view the application.


### 3. **State Management Design**

A clear state management strategy was essential for tracking the positions and properties of items on the board. The state was structured to include:
- A list of items, each with attributes such as height, width, and current x/y coordinates.
- A method to update the state whenever an item is moved, ensuring that the UI reflects these changes.

### 4. **Component Structure**

- **Board Component:** This serves as the container for all movable items and manages the overall layout.
- **Item Component:** Each draggable item is represented as a separate component, allowing for individual handling of drag events.

### 5. **Implementing Drag-and-Drop Functionality**

The core functionality of dragging and dropping items was implemented using native HTML5 drag-and-drop API features:
- Event handlers were defined for `startDrag`, `onDrag`, and `stopDrag` events to manage item movement and position updates effectively.
- Logic was incorporated to calculate new positions based on mouse coordinates when an item is dropped, updating the state accordingly.

### 6. **Styling and User Interface**

To ensure a clean and intuitive user interface:
- CSS used for styling, focusing on a minimalist design to enhance usability.
- Visual indicators were added to represent draggable items clearly, ensuring users understand which items can be moved.

### 7. **Testing and Validation**

After implementation, thorough testing was conducted to ensure:
- Items could be moved without any glitches.
- The state correctly updated upon item movement.
- The user interface was responsive and intuitive, catering to various screen sizes.

### 8. **Documentation**

The README.md documentation was created to include:
- An overview of the project and its purpose.
- Detailed instructions on installation and usage.
- Explanations of state management and design decisions.
- A clear description of the code structure to help future developers understand the flow of the application.

## Conclusion

The approach taken for this project was comprehensive and methodical, ensuring that all requirements were met while adhering to best practices in code structure and user experience. The decision to avoid third-party libraries highlighted the ability to leverage core JavaScript and React capabilities, resulting in a robust and functional application.
