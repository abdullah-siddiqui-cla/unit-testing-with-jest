# Exercise 1: Testing Utility Functions
Create a file with utility functions, such as calculating the sum of two numbers and checking if a number is even.

### `File: utils.js`

```
function add(a, b) {
  return a + b;
}

function isEven(num) {
  return num % 2 === 0;
}

module.exports = { add, isEven };
```

### Task:

- Write tests for the `add` and `isEven` functions.
- Cover edge cases, such as `negative numbers` and `zero`.

Solution File: `Solution File: utils.test.js`

# Exercise 2: Testing an Asynchronous Function
Create a file with a function that fetches user data (mock the API call for simplicity).

### `File: userService.js`

```
async function getUser(id) {
  if (!id) throw new Error('Invalid user ID');
  return { id, name: 'John Doe' };
}

module.exports = { getUser };
```

### Task:
- Write tests for `getUser`.
- Test success and failure scenarios (invalid ID).

Solution File: `userService.test.js`

# Bonus Exercise 3: Mocking External Modules
Test a file that depends on another module using mocks.

### `File: orderService.js`

```
const paymentService = require('./paymentService');

function placeOrder(order) {
  if (!order) throw new Error('Order details are required');
  const payment = paymentService.processPayment(order.amount);
  return { order, payment };
}

module.exports = { placeOrder };
```

### `File: paymentService.js`

```
function processPayment(amount) {
  return `Payment of $${amount} processed`;
}

module.exports = { processPayment };
```

### Task:

- Write a test for `placeOrder`.
- Mock `processPayment` to avoid calling the actual function.
