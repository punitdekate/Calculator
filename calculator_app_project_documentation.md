
# Calculator App - Project Documentation

## 1. **Introduction**

The **Calculator App** is a simple application that mimics a traditional calculator. It allows users to perform basic arithmetic operations like addition, subtraction, multiplication, and division. The app uses **React** for the frontend and **Redux Toolkit** for state management.

---

## 2. **Features**

### 2.1 Input Numbers
Users can input numbers by clicking on the numeric buttons. The input will be displayed on the screen.

### 2.2 Arithmetic Operations
Users can perform basic arithmetic operations such as addition, subtraction, multiplication, and division.

### 2.3 Clear Input
Users can clear the input, resetting the calculator's state.

### 2.4 Calculate Result
After inputting numbers and operations, users can press the equals button to calculate and display the result.

---

## 3. **Technologies Used**

- **Frontend**: React
- **State Management**: Redux Toolkit
- **JavaScript**: ES6

---

## 4. **Folder Structure**

```
/src
  /components
    Calculator.js       // Main calculator component containing buttons and display
  /redux
    calculator.reducer.js // Contains actions and reducers for calculator logic
  App.js                 // Main app component to render the calculator
  index.js               // Entry point for React app
  /styles
    styles.css           // Global styles for the app
```

---

## 5. **State Management with Redux**

### 5.1 Redux Store Structure

The state of the app is managed using Redux and contains the following structure:

```javascript
{
  input: "",         // Current input displayed on the calculator
  lastIn: null       // The last entered value or operation
}
```

### 5.2 Actions and Reducers

#### 5.2.1 Add Number

The `addNum` action updates the `input` state by appending the entered number.

```javascript
addNum: (state, action) => {
  state.input += action.payload;
  state.lastIn = action.payload;
}
```

#### 5.2.2 Add Operation

The `addOp` action updates the `input` state by adding the selected arithmetic operation.

```javascript
addOp: (state, action) => {
  state.input += " " + action.payload + " ";
  state.lastIn = action.payload;
}
```

#### 5.2.3 Clear Input

The `clearInput` action clears the current input and resets the state.

```javascript
clearInput: (state) => {
  state.input = "";
  state.lastIn = null;
}
```

#### 5.2.4 Equals Output

The `equalsOutput` action updates the `input` state with the calculated result.

```javascript
equalsOutput: (state, action) => {
  state.input = action.payload;
  state.lastIn = action.payload;
}
```

---

## 6. **Components**

### 6.1 Calculator

The `Calculator` component renders the calculator layout. It includes buttons for digits (0-9), arithmetic operators (+, -, *, /), as well as the equals button and a clear button. The input is displayed on the screen.

---

## 7. **Redux Flow**

### 7.1 Add Number

When a number is clicked, the `addNum` action is dispatched with the clicked number as the payload.

### 7.2 Add Operation

When an operator is clicked, the `addOp` action is dispatched with the selected operator as the payload.

### 7.3 Clear Input

When the clear button is clicked, the `clearInput` action is dispatched, which resets the calculator's input.

### 7.4 Calculate Result

When the equals button is clicked, the `equalsOutput` action is dispatched, and the current input is evaluated to produce the result.

---

## 8. **Styling**

The app uses basic CSS to style the calculator. Each button is styled to appear similar to a physical calculator, and the display area is adjusted to show the input clearly.

---

## 9. **Running the Project**

### 9.1 Prerequisites

- Node.js
- NPM (Node Package Manager)

### 9.2 Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/calculator-app.git
cd calculator-app
```

2. Install dependencies:

```bash
npm install
```

3. Start the app:

```bash
npm start
```

The app should now be running on [http://localhost:3000](http://localhost:3000).

---

## 10. **Conclusion**

The Calculator App is a simple and functional app that allows users to perform basic arithmetic operations. It utilizes **React** and **Redux Toolkit** for state management and UI rendering, providing a clean and interactive user experience.

---
