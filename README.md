<div align="center">
   <img height="60" <img src="https://github.com/user-attachments/assets/9f63eddd-c0a7-4ed5-a7dc-f3d817c4c6af" height="60" alt="Image">
  <h1> React-ChallengeHub </h1>
</div> 

> [!NOTE]   
> This repository was created in 2024, so the questions reflect React syntax and features from that time. React evolves rapidly, and newer features may not be covered here.

---

<p align="center">
From basic to advanced: test your React knowledge, refresh your skills, or prepare for coding interviews! 💪🚀 I regularly update this repo with new questions. Answers are available in the **collapsed sections** below each question—just click to expand. Have fun and good luck! ❤️</p>

<p align="center">Feel free to connect with me! 😊</p>

<p align="center">
  <a href="https://www.instagram.com/_lokesh___3983">Instagram</a> || <a href="https://twitter.com/Not_LokeshSingh">Twitter</a> ||
  <a href="https://dev.to/lokesh_singh">Blog</a> || <a href="https://github.com/Lokeshsingh78">GitHub</a>
</p>

| Feel free to use these questions in your projects! 😃 I would _really_ appreciate a reference to this repo. I create the questions and explanations (yes, I do it with a bit of sadness lol), and the community helps maintain and improve them! 💪🏼 Thank you and enjoy! |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
---

###### 1. What's the output?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount(10);
  }, []);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 0
- B: 10
- C: undefined
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` hook runs after the initial render, and it updates the `count` state to `10`. So, the component will display `10`.

</p>
</details>

---

###### 2. What happens when you call `setState` in a React component?

- A: The component re-renders immediately.
- B: The state is updated synchronously.
- C: The component re-renders after a short delay.
- D: The state is updated asynchronously, and the component re-renders.

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

`setState` in React is asynchronous, meaning it does not immediately update the state but schedules an update. The component will re-render after the state has been updated.

</p>
</details>

---

###### 3. What's the output?

```jsx
const MyComponent = () => {
  const [value, setValue] = React.useState("Initial Value");

  const handleClick = () => {
    setValue((prev) => prev + " Updated");
  };

  return <button onClick={handleClick}>{value}</button>;
};

ReactDOM.render(<MyComponent />, document.getElementById('root'));
```

- A: "Initial Value"
- B: "Initial Value Updated"
- C: "Initial Value" on first click, "Initial Value Updated" on subsequent clicks
- D: "Initial Value Updated" on first click, "Initial Value Updated Updated" on subsequent clicks

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

On the first click, the button text will change to "Initial Value Updated". On subsequent clicks, " Updated" will keep appending to the text.

</p>
</details>

---

###### 4. What's the output?

```jsx
const App = () => {
  const [text, setText] = React.useState("");

  React.useEffect(() => {
    setText("Hello");
  }, []);

  return <input value={text} />;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: An empty input field
- B: Input field with "Hello"
- C: Error
- D: Input field with "undefined"

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` hook sets the `text` state to "Hello" after the component mounts, so the input field displays "Hello".

</p>
</details>

---

###### 5. What's true about `useMemo` in React?

- A: It re-runs the calculation on every render.
- B: It memorizes a calculation and only recalculates when its dependencies change.
- C: It replaces the need for `useEffect`.
- D: It prevents a component from re-rendering.

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useMemo` is used to memoize expensive calculations and will only re-run the calculation if the specified dependencies change.

</p>
</details>

---

###### 6. What's the output?

```jsx
const App = () => {
  const [number, setNumber] = React.useState(1);

  React.useEffect(() => {
    setNumber(number + 1);
  }, [number]);

  return <div>{number}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 1
- B: 2
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The `useEffect` hook has a dependency on `number`, and since `setNumber` changes `number`, it triggers the effect again, causing an infinite loop.

</p>
</details>

---

###### 7. What's the output?

```jsx
const App = () => {
  const [state, setState] = React.useState({ count: 0 });

  const increment = () => {
    setState({ count: state.count + 1 });
  };

  return (
    <div>
      <button onClick={increment}>Increment</button>
      <p>{state.count}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 0
- B: 1
- C: 2
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The button increments the `count` value by 1 each time it is clicked, but initially, it displays `0`.

</p>
</details>

---

###### 8. What will be logged in the console?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount(count + 1);
    console.log(count);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 0
- B: 1
- C: 0 and 1
- D: Infinite loop

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The `console.log` will log the previous value of `count` (which is `0` initially), and then `count` will be updated to `1` after the effect runs. However, this can lead to an infinite loop, so this code should be avoided.

</p>
</details>

---

###### 9. Which one is true about `React.Fragment`?

- A: It renders multiple children in a list without adding extra nodes to the DOM.
- B: It renders children inside a single `<div>`.
- C: It's the same as returning an array of elements.
- D: It adds a wrapper `<div>` around the children.

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`React.Fragment` lets you group a list of children without adding extra nodes to the DOM.

</p>
</details>

---

###### 10. What happens when you use `React.StrictMode`?

- A: It activates additional checks and warnings for its descendants.
- B: It prevents components from re-rendering.
- C: It enforces strict type checking.
- D: It disables deprecated features in React.

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`React.StrictMode` doesn't render anything to the DOM. It only activates additional checks and warnings for the components within it.

</p>
</details>

---

###### 11. What's the output?

```jsx
const Counter = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount(count + 1);
  }, []);

  React.useEffect(() => {
    setCount(count + 1);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<Counter />, document.getElementById('root'));
```

- A: 0
- B: 1
- C: 2
- D: Infinite loop

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

In this example, the first `useEffect` runs after the initial render and sets the `count` to `1`. The second `useEffect` runs whenever `count` changes, causing `count` to increment by `1` every time it changes. This creates an infinite loop where `count` keeps increasing indefinitely.

</p>
</details>

---

###### 12. What is the output of the following code?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  React.useEffect(() => {
    setValue((prev) => prev + 1);
    setValue((prev) => prev + 1);
  }, []);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 1
- B: 2
- C: 3
- D: 0

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` hook will execute its callback after the initial render. Inside the `useEffect`, two `setValue` calls are made. However, React batches state updates in the same event loop. Therefore, both updates are applied to the previous state (which is `0`), resulting in `value` being `2`.

</p>
</details>

---

###### 13. What's the output?

```jsx
const App = () => {
  const [text, setText] = React.useState("");

  const handleClick = () => {
    setText("Clicked!");
  };

  React.useEffect(() => {
    setText("Updated!");
  }, []);

  return <button onClick={handleClick}>{text}</button>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: "Clicked!" initially, "Updated!" on click
- B: "Updated!" initially, "Clicked!" on click
- C: "Updated!" both initially and on click
- D: "Clicked!" both initially and on click

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` hook sets the `text` state to "Updated!" immediately after the initial render. The button text displays "Updated!" initially. On click, `handleClick` changes the `text` state to "Clicked!", so the button text changes to "Clicked!" when clicked.

</p>
</details>

---

###### 14. What is the result of the following code?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = () => setCount(count + 1);

  return (
    <div>
      <button onClick={increment}>Increment</button>
      <p>{count}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The button increments the count by 1 on each click
- B: The count remains at 0
- C: The button does not update the count
- D: The count increments by 2 on each click

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `increment` function updates the state with `count + 1`. React batches state updates, but the new state value is computed from the current value, so each button click correctly increments the count by 1.

</p>
</details>

---

###### 15. What's the output?

```jsx
const App = () => {
  const [items, setItems] = React.useState([1, 2, 3]);

  React.useEffect(() => {
    setItems([...items, items.length + 1]);
  }, [items]);

  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: [1, 2, 3, 4]
- B: Infinite loop
- C: [1, 2, 3]
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` depends on `items`, and `setItems` updates `items` by adding a new item. This triggers `useEffect` again, leading to an infinite loop as each update causes another effect to run.

</p>
</details>

---

###### 16. What happens with the following code?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  const handleClick = () => setValue((v) => v + 1);

  React.useEffect(() => {
    handleClick();
  }, []);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The value is 1
- B: The value is 0
- C: The value is 2
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`useEffect` runs after the initial render and calls `handleClick`, which increments the value by 1. Thus, the value displayed is `1`.

</p>
</details>

---

###### 17. What's the output of this code?

```jsx
const App = () => {
  const [data, setData] = React.useState({ name: "John", age: 25 });

  const updateData = () => {
    setData((prevData) => ({ ...prevData, age: prevData.age + 1 }));
  };

  React.useEffect(() => {
    updateData();
  }, []);

  return <div>{data.age}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 25
- B: 26
- C: 27
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` runs once after the initial render and calls `updateData`, which updates `age` to `26`. Therefore, `data.age` is `26`.

</p>
</details>

---

###### 18. What is the result of the following code?

```jsx
const App = () => {
  const [items, setItems] = React.useState([]);

  const addItem = () => {
    setItems((prevItems) => [...prevItems, prevItems.length + 1]);
  };

  React.useEffect(() => {
    addItem();
  }, []);

  return <ul>{items.map((item) => <li key={item}>{item}</li>)}</ul>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: [1]
- B: [1, 2]
- C: Empty list
- D: Infinite loop

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`useEffect` runs once after the initial render and calls `addItem`, adding `1` to the `items` array. The list displays `[1]`.

</p>
</details>

---

###### 19. What's the output?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    const timer = setTimeout(() => setCount(count + 1), 1000);
    return () => clearTimeout(timer);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The count increments every second
- B: The count remains at 0
- C: The count increments by 2 every second
- D: Infinite loop

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` sets up a timeout that increments `count` after 1 second. Since `count` is a dependency, the effect cleans up (clears the timer) and re-runs with each update. This results in the count incrementing every second.

</p>
</details>

---

###### 20. What's the output?

```jsx
const App = () => {
  const [data, setData] = React.useState({ count: 0 });

  const increment = () => {
    setData((prev) => ({ ...prev, count: prev.count + 1 }));
  };

  React.useEffect(() => {
    increment();
  }, []);

  return <div>{data.count}</div>;
};

ReactDOM.render(<App />, document.getElementById

('root'));
```

- A: 0
- B: 1
- C: 2
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` runs after the initial render and calls `increment`, which increases the `count` by 1. Thus, the displayed value is `1`.

</p>
</details>

---

###### 21. What is the result of the following code?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  const increment = () => {
    setValue((prev) => prev + 1);
  };

  React.useEffect(() => {
    increment();
  }, [value]);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The value increments every second
- B: Infinite loop
- C: The value remains 0
- D: The value increments by 1

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` runs every time `value` changes, and `increment` updates `value` by 1. This creates an infinite loop as `value` keeps changing, which continually triggers the `useEffect`.

</p>
</details>

---

###### 22. What is the output of this code?

```jsx
const App = () => {
  const [data, setData] = React.useState({ name: "Alice" });

  React.useEffect(() => {
    setData((prev) => ({ ...prev, name: "Bob" }));
  }, []);

  return <div>{data.name}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: "Alice"
- B: "Bob"
- C: "undefined"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` runs after the initial render and updates `data` with `{ name: "Bob" }`. Thus, the displayed name is "Bob".

</p>
</details>

---

###### 23. What will happen with this code?

```jsx
const App = () => {
  const [number, setNumber] = React.useState(0);

  const updateNumber = () => setNumber(number + 1);

  React.useEffect(() => {
    updateNumber();
  }, []);

  return <div>{number}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The number is 0
- B: The number is 1
- C: The number is 2
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` runs after the initial render and calls `updateNumber`, which increases `number` by 1. Thus, the displayed number is `1`.

</p>
</details>

---

###### 24. What is the output?

```jsx
const App = () => {
  const [isVisible, setIsVisible] = React.useState(true);

  React.useEffect(() => {
    setIsVisible(false);
  }, []);

  return <div>{isVisible ? "Visible" : "Hidden"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: "Visible"
- B: "Hidden"
- C: "Visible" and then "Hidden"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` runs after the initial render and sets `isVisible` to `false`. Therefore, the displayed text is "Hidden".

</p>
</details>

---

###### 25. What is the result of this code?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    if (count === 5) {
      setCount(0);
    }
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The count will be 0, 1, 2, 3, 4, and then reset to 0
- B: The count will increment indefinitely
- C: The count will remain 0
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` sets `count` to `0` when it reaches `5`, which triggers another `useEffect` run, causing an infinite loop as the count keeps resetting.

</p>
</details>

---

###### 26. What does this code output?

```jsx
const App = () => {
  const [list, setList] = React.useState([]);

  const addItem = () => {
    setList((prevList) => [...prevList, prevList.length + 1]);
  };

  React.useEffect(() => {
    addItem();
    addItem();
  }, []);

  return (
    <ul>
      {list.map((item) => (
        <li key={item}>{item}</li>
      ))}
    </ul>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: [1, 2]
- B: [1]
- C: []
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`useEffect` calls `addItem` twice, so two items are added to the `list` (`[1, 2]`). Therefore, the list displays `[1, 2]`.

</p>
</details>

---

###### 27. What will this code display?

```jsx
const App = () => {
  const [number, setNumber] = React.useState(0);

  React.useEffect(() => {
    const interval = setInterval(() => setNumber((n) => n + 1), 1000);
    return () => clearInterval(interval);
  }, []);

  return <div>{number}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Number increments by 1 every second
- B: Number remains 0
- C: Number increments by 2 every second
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` sets up an interval that increments `number` by 1 every second. The interval is cleared on component unmount, so the number increments by 1 every second while the component is mounted.

</p>
</details>

---

###### 28. What is the result of the following code?

```jsx
const App = () => {
  const [data, setData] = React.useState({ count: 0 });

  React.useEffect(() => {
    setData({ count: data.count + 1 });
  }, [data]);

  return <div>{data.count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Count is 1
- C: Count is 0
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` depends on `data`, and `setData` updates `data`, which triggers the effect again. This creates an infinite loop, as each update triggers another effect.

</p>
</details>

---

###### 29. What is the result of the following code?

```jsx
const App = () => {
  const [items, setItems] = React.useState([1]);

  React.useEffect(() => {
    setItems((prev) => [...prev, prev.length + 1]);
  }, []);

  return (
    <ul>
      {items.map((item) => (
        <li key={item}>{item}</li>
      ))}
    </ul>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: [1, 2]
- B: [1]
- C: [1, 2, 3]
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` runs once and adds `2` to the `items` array. Thus, the displayed list is `[1, 2]`.

</p>
</details>

---

###### 30. What happens with this code?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    if (show) {
      console.log("Showing");
    } else {
      console.log("Hiding");
    }
  }, [show]);

  return (
    <div>
      <button onClick={() => setShow(!show)}>Toggle</button>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Logs "Showing" when `show` is true, "Hiding" when `show` is false
- B: Logs "Showing" only
- C: Logs "Hiding" only
- D: No log output

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` logs "Showing" when `show` is `true` and "Hiding" when `show` is `false`. Each time the button is clicked, the effect runs and logs the appropriate message.

</p>
</details>

---

###### 31. What is the output of this code?

```jsx
const App = () => {
  const [text, setText]

 = React.useState("Hello");

  const handleClick = () => setText("World");

  React.useEffect(() => {
    handleClick();
  }, []);

  return <div>{text}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: "Hello"
- B: "World"
- C: "HelloWorld"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` runs after the initial render and calls `handleClick`, which sets `text` to "World". Therefore, the displayed text is "World".

</p>
</details>

---

###### 32. What is the result of this code?

```jsx
const App = () => {
  const [state, setState] = React.useState({ count: 0 });

  React.useEffect(() => {
    setState((prevState) => ({ count: prevState.count + 1 }));
  }, []);

  return <div>{state.count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The count increments every render
- B: The count is 0
- C: The count is 1
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

`useEffect` runs only once after the initial render and increments `count` by 1. Therefore, the displayed count is `1`.

</p>
</details>

---

###### 33. What will happen with this code?

```jsx
const App = () => {
  const [inputValue, setInputValue] = React.useState("");

  React.useEffect(() => {
    console.log(inputValue);
  }, [inputValue]);

  return (
    <input
      value={inputValue}
      onChange={(e) => setInputValue(e.target.value)}
    />
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Logs the input value every time it changes
- B: Logs an empty string
- C: Logs the initial value only
- D: No log output

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` logs `inputValue` every time it changes due to the dependency array containing `inputValue`. As the input changes, the new value is logged.

</p>
</details>

---

###### 34. What is the result of this code?

```jsx
const App = () => {
  const [data, setData] = React.useState(null);

  React.useEffect(() => {
    fetch("/api/data")
      .then((response) => response.json())
      .then((result) => setData(result));
  }, []);

  return <div>{data ? "Data loaded" : "Loading data..."}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Loading data..." until data is fetched
- B: Displays "Data loaded" immediately
- C: Displays "Loading data..." and then "Data loaded"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

`useEffect` initiates a fetch request and updates `data` once the request completes. Initially, it displays "Loading data...", and after fetching, it displays "Data loaded".

</p>
</details>

---

###### 35. What is the result of this code?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    console.log("Component mounted");
    return () => console.log("Component unmounted");
  }, []);

  return (
    <div>
      {show && <div>Visible</div>}
      <button onClick={() => setShow(!show)}>Toggle</button>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Logs "Component mounted" and "Component unmounted" on mount and unmount
- B: Logs "Component mounted" only
- C: Logs "Component unmounted" only
- D: No log output

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` logs "Component mounted" when the component is mounted and "Component unmounted" when it is unmounted, thanks to the cleanup function returned from `useEffect`.

</p>
</details>

---

###### 36. What will this code output?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    const timer = setTimeout(() => setCount(count + 1), 1000);
    return () => clearTimeout(timer);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: The count increments every second
- B: The count is 0 and never changes
- C: The count increments by 2 every second
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`useEffect` sets a timeout that updates `count` after 1 second. Each update clears the previous timeout and sets a new one, causing the count to increment every second.

</p>
</details>

---

###### 37. What is the result of this code?

```jsx
const App = () => {
  const [value, setValue] = React.useState("initial");

  React.useEffect(() => {
    setValue("updated");
  }, []);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: "initial"
- B: "updated"
- C: Error
- D: "initialupdated"

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` runs after the initial render and updates `value` to "updated". Therefore, the displayed value is "updated".

</p>
</details>

---

###### 38. What is the result of the following code?

```jsx
const App = () => {
  const [input, setInput] = React.useState("");

  React.useEffect(() => {
    if (input) {
      console.log(`Input changed: ${input}`);
    }
  }, [input]);

  return (
    <input
      type="text"
      value={input}
      onChange={(e) => setInput(e.target.value)}
    />
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Logs "Input changed" only if `input` is not empty
- B: Logs "Input changed" regardless of input
- C: No log output
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`useEffect` logs the input change only if `input` is not empty. The log occurs when `input` changes to a non-empty value.

</p>
</details>

---

###### 39. What is the output of this code?

```jsx
const App = () => {
  const [data, setData] = React.useState([]);

  React.useEffect(() => {
    setData([1, 2, 3]);
  }, []);

  return <div>{data.length}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 0
- B: 1
- C: 3
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: 3

The `useEffect` sets `data` to `[1, 2, 3]` after the initial render. Thus, the length of `data` is `3`.

</p>
</details>

---

###### 40. What is the result of the following code?

```jsx
const App = () => {
  const [text, setText] = React.useState("Initial");

  React.useEffect(() => {
    setText("Changed");
  }, []);

  return <div>{text}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: "Initial"
- B: "Changed"
- C: Error
- D: "InitialChanged"

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`useEffect` updates `text` to "Changed" after the initial render. Therefore, the displayed text is "Changed".

</p>
</details>

---

###### 41. What will this code display?

```jsx
const App = () => {
  const [items, setItems] = React.useState([]);

  React.useEffect(() => {
    setItems(["Item 1", "Item 2"]);
  }, []);

  React.useEffect(() => {
    console.log(items);
  }, [items]);

  return <div>{items.join(", ")}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Logs an empty array and displays "Item 1, Item 2"
- B: Logs ["Item 1", "Item 2"] and displays "Item 1, Item 2"
- C: Logs ["Item 1", "Item 2"] and displays an empty string
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The first `useEffect` updates `items` to `["Item 1", "Item 2"]`. The second `useEffect` logs `items` whenever it changes. Thus, "Item 1, Item 2" is displayed, and `["Item 1", "Item 2"]` is logged.

</p>
</details>

---

###### 42. What is the result of this code?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = () => setCount(count + 1);

  return (
    <div>
      <button onClick={increment}>Increment</button>
      <p>{count}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Clicking the button increments the count correctly
- B: Clicking the button does not update the count
- C: Clicking the button sets count to 1
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `increment` function updates `count` correctly when the button is clicked, causing the count to increment.

</p>
</details>

---

###### 43. What is the output of the following code?

```jsx
const App = () => {
  const [data, setData] = React.useState([1, 2, 3]);

  const removeItem = () => {
    setData((prevData) => prevData.slice(0, -1));
  };

  return (
    <div>
      <button onClick={removeItem}>Remove Last Item</button>
      <ul>
        {data.map((item) => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays a list of items with the last item removed on button click
- B: Displays the list unchanged on button click
- C: Displays an error on button click
- D: Displays an empty list on button click

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `removeItem` function updates the `data` state by removing the last item from the array. Therefore, the displayed list updates with the last item removed when the button is clicked.

</p>
</details>

---

###### 44. What does this code do?

```jsx
const App = () => {
  const [input, setInput] = React.useState("");

  React.useEffect(() => {
    const handleKeyPress = (e) => {
      setInput((prev) => prev + e.key);
    };

    window.addEventListener("keypress", handleKeyPress);

    return () => {
      window.removeEventListener("keypress", handleKeyPress);
    };
  }, []);

  return <div>{input}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Appends key presses to the input string
- B: Clears the input string on key press
- C: Logs key presses to the console
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` adds an event listener for key presses and appends the pressed keys to the `input` state. The event listener is cleaned up when the component unmounts.

</p>
</details>

---

###### 45. What is the output of this code?

```jsx
const App = () => {
  const [number, setNumber] = React.useState(1);

  React.useEffect(() => {
    setNumber(2);
  }, []);

  React.useEffect(() => {
    setNumber(3);
  }, []);

  return <div>{number}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: 1
- B: 2
- C: 3
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The second `useEffect` runs after the first one, setting `number` to `3`. Therefore, the displayed value is `3`.

</p>
</details>

---

###### 46. What will this code display?

```jsx
const App = () => {
  const [items, setItems] = React.useState(["Item 1"]);

  const addItem = () => {
    setItems((prev) => [...prev, `Item ${prev.length + 1}`]);
  };

  return (
    <div>
      <button onClick={addItem}>Add Item</button>
      <ul>
        {items.map((item) => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Adds an item to the list on button click
- B: Adds multiple items to the list on button click
- C: Displays only one item in the list
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `addItem` function appends a new item to the `items` array each time the button is clicked, causing the list to grow with each click.

</p>
</details>

---

###### 47. What is the result of the following code?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  return (
    <div>
      {show && <p>Hello</p>}
      <button onClick={() => setShow(!show)}>Toggle</button>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles the visibility of "Hello" on button click
- B: Displays "Hello" permanently
- C: Hides "Hello" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `show` state controls the visibility of the `<p>` element with "Hello". Clicking the button toggles the `show` state, thereby toggling the visibility of "Hello".

</p>
</details>

---

###### 48. What is the output of this code?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = () => setCount((prev) => prev + 1);

  React.useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <button onClick={increment}>Increment</button>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Updates the document title with the count value
- B: Does not update the document title
- C: Throws an error
- D: Updates the document title to "Count: 0"

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

`useEffect` updates the document title every time the `count` changes. Thus, clicking the button will update the title to reflect the current count value.

</p>
</details>

---

###### 49. What will this code display?

```jsx
const App = () => {
  const [value, setValue] = React.useState("");

  const handleChange = (e) => {
    setValue(e.target.value);
  };

  return (
    <input type="text" value={value} onChange={handleChange} />
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: A text input field that updates as the user types
- B: A text input field that does not update
- C: An error occurs
- D: A non-editable text field

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `handleChange` function updates the `value` state with the input's value, making the input field controlled and reflecting user input.

</p>
</details>

---

###### 50. What is the result of this code?

```jsx
const App = () => {
  const [data, setData] = React.useState(null);

  React.useEffect(() => {
    fetch("/api/data")
      .then((response) => response.json())
      .then((result) => setData(result));
  }, []);

  return

 <div>{data ? JSON.stringify(data) : "Loading..."}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Loading..." until data is fetched, then displays the fetched data
- B: Displays "Loading..." only
- C: Displays an error
- D: Displays the initial data

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The code shows "Loading..." while the data is being fetched. Once the data is fetched and `data` is updated, it displays the fetched data as a JSON string.

</p>
</details>

---

###### 51. What will this code display?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <button onClick={increment}>Increment</button>
      <p>{count}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Increment button will not update the count
- B: Clicking the button will display the count correctly
- C: Displays "0" and does not change
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `increment` function updates the `count` state by adding `1` to its current value. Clicking the button correctly updates the displayed count.

</p>
</details>

---

###### 52. What does this code do?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  return (
    <div>
      {show && <h1>Hello World</h1>}
      <button onClick={() => setShow(!show)}>Toggle</button>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Hello World" and toggles its visibility
- B: Displays "Hello World" permanently
- C: Hides "Hello World" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `show` state controls whether the `<h1>` element is displayed or not. The button toggles the `show` state, thereby toggling the visibility of "Hello World".

</p>
</details>

---

###### 53. What is the output of the following code?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, []);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays 1
- B: Displays 2
- C: Displays 3
- D: Displays 0

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

The first `useEffect` runs once on mount and increments `count` to `1`. The second `useEffect` runs on every `count` change, incrementing `count` again, leading to a final value of `3`.

</p>
</details>

---

###### 54. What will be displayed by this code?

```jsx
const App = () => {
  const [data, setData] = React.useState([1, 2, 3]);

  React.useEffect(() => {
    setData((prev) => prev.filter((item) => item !== 2));
  }, []);

  return <div>{data.join(", ")}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1, 2, 3"
- B: Displays "1, 3"
- C: Displays "2"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` filters out the item `2` from the `data` array, so the displayed result is "1, 3".

</p>
</details>

---

###### 55. What is the result of this code?

```jsx
const App = () => {
  const [input, setInput] = React.useState("");

  const handleChange = (e) => {
    setInput(e.target.value);
  };

  return (
    <div>
      <input type="text" value={input} onChange={handleChange} />
      <p>{input}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays the input value below the text field
- B: Displays an error
- C: The input field remains unchanged
- D: Displays a fixed string below the text field

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The input value is updated and displayed below the text field in real-time as the user types.

</p>
</details>

---

###### 56. What does this code demonstrate?

```jsx
const App = () => {
  const [value, setValue] = React.useState("Initial");

  return (
    <div>
      <button onClick={() => setValue("Updated")}>Update</button>
      <p>{value}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Updates the text in the `<p>` element when the button is clicked
- B: Displays the text "Initial" permanently
- C: Updates the button text instead of `<p>`
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `setValue` function updates the state, and clicking the button changes the displayed text in the `<p>` element to "Updated".

</p>
</details>

---

###### 57. What will this code output?

```jsx
const App = () => {
  const [data, setData] = React.useState([1, 2, 3]);

  React.useEffect(() => {
    setData((prev) => [...prev, 4]);
  }, []);

  return <div>{data.join(", ")}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1, 2, 3, 4"
- B: Displays "1, 2, 3"
- C: Displays "4"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` adds `4` to the `data` array on mount, resulting in the display of "1, 2, 3, 4".

</p>
</details>

---

###### 58. What does this code do?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  const handleClick = () => {
    setValue((prev) => prev + 1);
  };

  return (
    <div>
      <button onClick={handleClick}>Increment</button>
      <p>{value}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Increments the value and displays it
- B: Displays the value as "0" permanently
- C: Increments the value but does not display it
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `handleClick` function increments the `value` state and updates the `<p>` element to reflect the new value.

</p>
</details>

---

###### 59. What is the result of this code?

```jsx
const App = () => {
  const [items, setItems] = React.useState([1, 2, 3]);

  const removeLastItem = () => {
    setItems((prev) => prev.slice(0, -1));
  };

  return (
    <div>
      <button onClick={removeLastItem}>Remove Last Item</button>
      <ul>
        {items.map((item) => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Removes the last item from the list and updates the display
- B: Does not update the list
- C: Displays only the last item
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `removeLastItem` function updates the `items` state by removing the last item from the list, causing the list to update accordingly.

</p>
</details>

---

###### 60. What will this code display?

```jsx
const App = () => {
  const [data, setData] = React.useState(null);

  React.useEffect(() => {
    fetch("/api/data")
      .then((response) => response.json())
      .then((result) => setData(result));
  }, []);

  return <div>{data ? "Data Loaded" : "Loading..."}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Loading..." until data is fetched, then "Data Loaded"
- B: Displays "Loading..." permanently
- C: Displays "Data Loaded" immediately
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

Initially, "Loading..." is displayed. Once data is fetched and `data` is updated, "Data Loaded" is shown.

</p>
</details>

---

###### 61. What is the output of this code?

```jsx


const App = () => {
  const [data, setData] = React.useState([1, 2, 3]);

  React.useEffect(() => {
    setData((prev) => [...prev, 4]);
  }, [data]);

  return <div>{data.join(", ")}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays "1, 2, 3, 4"
- C: Displays "4"
- D: Displays "1, 2, 3"

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` runs on every `data` change, leading to an infinite loop as `data` is continually updated.

</p>
</details>

---

###### 62. What will this code output?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  return (
    <div>
      {show ? <h1>Visible</h1> : <h1>Not Visible</h1>}
      <button onClick={() => setShow(!show)}>Toggle</button>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Alternates between "Visible" and "Not Visible"
- B: Displays "Visible" permanently
- C: Displays "Not Visible" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `show` state toggles between `true` and `false`, switching the displayed text between "Visible" and "Not Visible".

</p>
</details>

---

###### 63. What does this code illustrate?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = React.useCallback(() => {
    setCount((prev) => prev + 1);
  }, []);

  return (
    <div>
      <button onClick={increment}>Increment</button>
      <p>{count}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: `increment` function is memoized to prevent unnecessary re-renders
- B: `increment` function updates `count` incorrectly
- C: `increment` function does not update `count`
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useCallback` hook memoizes the `increment` function to prevent it from being recreated on every render, thus optimizing performance.

</p>
</details>

---

###### 64. What is the result of the following code?

```jsx
const App = () => {
  const [value, setValue] = React.useState("");

  const handleInputChange = (e) => {
    setValue(e.target.value);
  };

  return (
    <div>
      <input type="text" onChange={handleInputChange} />
      <p>{value}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays the input value below the text field
- B: Displays a fixed string below the text field
- C: The input field remains unchanged
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `handleInputChange` function updates the `value` state with the input value, which is then displayed below the text field.

</p>
</details>

---

###### 65. What will this code show?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return <div>Count is {count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Updates the document title with the count value
- B: Displays the count only
- C: Updates the count value but not the document title
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates the document title with the current `count` value whenever `count` changes.

</p>
</details>

---

###### 66. What is the result of the following code?

```jsx
const App = () => {
  const [show, setShow] = React.useState(false);

  return (
    <div>
      <button onClick={() => setShow((prev) => !prev)}>Toggle</button>
      {show && <h1>Now You See Me!</h1>}
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Now You See Me!" when toggled
- B: Displays "Now You See Me!" permanently
- C: The `<h1>` element remains hidden
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `show` state toggles the visibility of the `<h1>` element based on its boolean value.

</p>
</details>

---

###### 67. What does this code do?

```jsx
const App = () => {
  const [items, setItems] = React.useState(["Item 1", "Item 2"]);

  const addItem = () => {
    setItems((prev) => [...prev, `Item ${prev.length + 1}`]);
  };

  return (
    <div>
      <button onClick={addItem}>Add Item</button>
      <ul>
        {items.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Adds a new item to the list with each button click
- B: Displays only the initial items
- C: Adds a new item but does not update the list
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `addItem` function adds a new item to the `items` array with each button click, updating the list displayed.

</p>
</details>

---

###### 68. What is the output of this code?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <button onClick={increment}>Increment</button>
      <p>{count}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays the count and updates it correctly
- B: Displays "0" and does not update
- C: Displays an error
- D: The button text changes instead of updating the count

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `increment` function updates the `count` state by adding `1`, and the updated count is displayed.

</p>
</details>

---

###### 69. What will this code display?

```jsx
const App = () => {
  const [data, setData] = React.useState([1, 2, 3]);

  React.useEffect(() => {
    const newData = [4, 5, 6];
    setData(newData);
  }, []);

  return <div>{data.join(", ")}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "4, 5, 6"
- B: Displays "1, 2, 3"
- C: Displays "0"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets `data` to `[4, 5, 6]` on mount, so "4, 5, 6" is displayed.

</p>
</details>

---

###### 70. What does this code illustrate?

```jsx
const App = () => {
  const [show, setShow] = React.useState(false);

  const handleClick = () => {
    setShow((prev) => !prev);
  };

  return (
    <div>
      <button onClick={handleClick}>Toggle</button>
      {show && <p>Content is now visible</p>}
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles the visibility of "Content is now visible"
- B: Displays "Content is now visible" permanently
- C: The button does not work
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `handleClick` function toggles the `show` state, which controls the visibility of the `<p>` element.

</p>
</details>

---

###### 71. What will this code display?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, [

count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays "1"
- C: Displays "0"
- D: Displays incremented values

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `count` on each change, causing an infinite loop because `count` changes continuously.

</p>
</details>

---

###### 72. What does this code do?

```jsx
const App = () => {
  const [text, setText] = React.useState("");

  return (
    <div>
      <input type="text" onChange={(e) => setText(e.target.value)} />
      <p>{text}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays input value below the text field
- B: Displays a fixed string below the text field
- C: Input field does not update
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `text` state updates with the input value, and it is displayed below the input field.

</p>
</details>

---

###### 73. What is the output of this code?

```jsx
const App = () => {
  const [isToggled, setIsToggled] = React.useState(false);

  return (
    <div>
      <button onClick={() => setIsToggled(!isToggled)}>Toggle</button>
      {isToggled && <h1>It is toggled!</h1>}
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "It is toggled!" when the button is clicked
- B: Displays "It is toggled!" permanently
- C: The button does not toggle the state
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `isToggled` state controls the visibility of the `<h1>` element, which appears when `isToggled` is `true`.

</p>
</details>

---

###### 74. What does this code show?

```jsx
const App = () => {
  const [text, setText] = React.useState("Hello");

  const handleClick = () => {
    setText("Hello, World!");
  };

  return (
    <div>
      <button onClick={handleClick}>Change Text</button>
      <p>{text}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Changes text to "Hello, World!" on button click
- B: Displays "Hello" permanently
- C: Displays "Hello, World!" permanently without a button
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `handleClick` function updates the `text` state to "Hello, World!" when the button is clicked.

</p>
</details>

---

###### 75. What will this code output?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, []);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1"
- B: Displays "0"
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `count` to `1` after the initial render, so it displays "1".

</p>
</details>

---

###### 76. What does this code illustrate?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    const timer = setTimeout(() => setShow(false), 3000);
    return () => clearTimeout(timer);
  }, []);

  return <div>{show ? "Visible" : "Not Visible"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Visible" for 3 seconds, then "Not Visible"
- B: Displays "Visible" permanently
- C: Displays "Not Visible" immediately
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets a timer to change `show` to `false` after 3 seconds, transitioning the text from "Visible" to "Not Visible".

</p>
</details>

---

###### 77. What will this code display?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  const increment = () => setValue(value + 1);

  React.useEffect(() => {
    const interval = setInterval(increment, 1000);
    return () => clearInterval(interval);
  }, [value]);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays the value incrementing every second
- C: Displays a static value
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets up an interval to increment `value` every second, which updates `value` and triggers the effect again, leading to an infinite loop.

</p>
</details>

---

###### 78. What does this code do?

```jsx
const App = () => {
  const [show, setShow] = React.useState(false);

  const toggleShow = () => setShow(!show);

  return (
    <div>
      <button onClick={toggleShow}>Toggle Show</button>
      {show && <h1>Show is True</h1>}
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles the display of "Show is True"
- B: Displays "Show is True" permanently
- C: The button does not toggle the display
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `show` state controls whether the `<h1>` element is displayed, and it toggles when the button is clicked.

</p>
</details>

---

###### 79. What will this code display?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  React.useEffect(() => {
    increment();
  }, []);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1"
- B: Displays "0"
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook calls `increment` after the initial render, updating `count` to `1`, so "1" is displayed.

</p>
</details>

---

###### 80. What does this code show?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  return (
    <div>
      <button onClick={() => setShow(!show)}>Toggle</button>
      {show && <p>Now you see me!</p>}
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles the visibility of the paragraph
- B: Displays the paragraph permanently
- C: The button does not toggle the paragraph
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `show` state toggles the visibility of the `<p>` element when the button is clicked.

</p>
</details>

---

###### 81. What will this code output?

```jsx
const App = () => {
  const [text, setText] = React.useState("Initial Text");

  const changeText = () => {
    setText("Changed Text");
  };

  return (
    <div>
      <button onClick={changeText}>Change Text</button>
      <p>{text}</p>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Changes text to "Changed Text" on button click
- B: Displays "Initial Text" permanently
- C: Displays "Changed Text" without a button
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `changeText` function updates the `text` state to "Changed Text" when the button is clicked.

</p>
</details>

---

###### 82. What does this code illustrate?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  const increment = () => {
    setValue((prev) => prev + 1);
  };

  React.use

Effect(() => {
    const timer = setTimeout(increment, 2000);
    return () => clearTimeout(timer);
  }, []);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays the value incrementing to 1 after 2 seconds
- B: Displays the value incrementing every 2 seconds
- C: Displays the value as "0" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets a timeout to increment `value` to `1` after 2 seconds, and it displays "1".

</p>
</details>

---

###### 83. What will this code display?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays incremented values
- C: Displays "0" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `count` on each change, causing an infinite loop because `count` changes continuously.

</p>
</details>

---

###### 84. What does this code show?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    const interval = setInterval(() => setShow((prev) => !prev), 1000);
    return () => clearInterval(interval);
  }, []);

  return <div>{show ? "Visible" : "Not Visible"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles between "Visible" and "Not Visible" every second
- B: Displays "Visible" permanently
- C: Displays "Not Visible" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets up an interval to toggle the `show` state every second, so it alternates between "Visible" and "Not Visible".

</p>
</details>

---

###### 85. What will this code display?

```jsx
const App = () => {
  const [text, setText] = React.useState("Initial");

  React.useEffect(() => {
    setText("Updated");
  }, []);

  return <div>{text}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Updated"
- B: Displays "Initial"
- C: Displays nothing
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `text` to "Updated" after the initial render, so it displays "Updated".

</p>
</details>

---

###### 86. What does this code illustrate?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    const timer = setTimeout(() => setCount(count + 1), 2000);
    return () => clearTimeout(timer);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays the value incrementing to 1 after 2 seconds
- B: Displays an incremented value every 2 seconds
- C: Displays the value as "0" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

The `useEffect` hook sets a timeout to increment `count` every 2 seconds, so it keeps updating the value.

</p>
</details>

---

###### 87. What will this code show?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    const timer = setInterval(() => setShow((prev) => !prev), 1000);
    return () => clearInterval(timer);
  }, []);

  return <div>{show ? "Show" : "Hide"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles between "Show" and "Hide" every second
- B: Displays "Show" permanently
- C: Displays "Hide" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets an interval to toggle the `show` state every second, resulting in alternating "Show" and "Hide".

</p>
</details>

---

###### 88. What does this code do?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  const increment = () => {
    setValue((prev) => prev + 1);
  };

  React.useEffect(() => {
    increment();
  }, []);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1" after the initial render
- B: Displays "0" permanently
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook calls `increment` after the initial render, so `value` is updated to "1".

</p>
</details>

---

###### 89. What will this code display?

```jsx
const App = () => {
  const [text, setText] = React.useState("Default");

  React.useEffect(() => {
    setText("Changed");
  }, []);

  return <div>{text}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "Changed"
- B: Displays "Default"
- C: Displays nothing
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `text` to "Changed" after the initial render, so "Changed" is displayed.

</p>
</details>

---

###### 90. What does this code show?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, []);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1"
- B: Displays "0"
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `count` to `1` after the initial render, so it displays "1".

</p>
</details>

---

###### 91. What does this code illustrate?

```jsx
const App = () => {
  const [show, setShow] = React.useState(false);

  React.useEffect(() => {
    const timer = setInterval(() => setShow((prev) => !prev), 1000);
    return () => clearInterval(timer);
  }, []);

  return <div>{show ? "Visible" : "Not Visible"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles between "Visible" and "Not Visible" every second
- B: Displays "Visible" permanently
- C: Displays "Not Visible" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets up an interval to toggle the `show` state every second, so it alternates between "Visible" and "Not Visible".

</p>
</details>

---

###### 92. What will this code display?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, [count]);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays incremented values
- C: Displays "0" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets `count` to `count + 1` on every render, which causes an infinite loop because `count` keeps changing.

</p>
</details>

---

###### 93. What does this code show?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    const timer = setTimeout(() => setShow(false), 3000);
    return () => clearTimeout(timer);
  }, []);

  return <div>{show ? "Visible" : "Not Visible"}</div>;
};

ReactDOM.render(<App />, document.getElementById

('root'));
```

- A: Displays "Visible" for 3 seconds, then "Not Visible"
- B: Displays "Visible" permanently
- C: Displays "Not Visible" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets a timeout to change `show` to `false` after 3 seconds, so it shows "Visible" initially and "Not Visible" after 3 seconds.

</p>
</details>

---

###### 94. What will this code display?

```jsx
const App = () => {
  const [text, setText] = React.useState("Initial");

  React.useEffect(() => {
    setText("Updated");
  }, [text]);

  return <div>{text}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays "Updated"
- C: Displays "Initial"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `text`, which causes the effect to run again, leading to an infinite loop.

</p>
</details>

---

###### 95. What does this code show?

```jsx
const App = () => {
  const [value, setValue] = React.useState(0);

  React.useEffect(() => {
    setValue((prev) => prev + 1);
  }, []);

  return <div>{value}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1"
- B: Displays "0"
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `value` to "1" after the initial render, so it shows "1".

</p>
</details>

---

###### 96. What will this code display?

```jsx
const App = () => {
  const [show, setShow] = React.useState(false);

  React.useEffect(() => {
    const interval = setInterval(() => setShow((prev) => !prev), 1000);
    return () => clearInterval(interval);
  }, []);

  return <div>{show ? "On" : "Off"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Toggles between "On" and "Off" every second
- B: Displays "On" permanently
- C: Displays "Off" permanently
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets up an interval to toggle the `show` state every second, so it alternates between "On" and "Off".

</p>
</details>

---

###### 97. What will this code show?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, []);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1"
- B: Displays "0"
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `count` to "1" after the initial render, so it shows "1".

</p>
</details>

---

###### 98. What does this code illustrate?

```jsx
const App = () => {
  const [text, setText] = React.useState("Hello");

  React.useEffect(() => {
    setText("World");
  }, [text]);

  return <div>{text}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Infinite loop
- B: Displays "World"
- C: Displays "Hello"
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook updates `text`, causing the effect to run again, resulting in an infinite loop.

</p>
</details>

---

###### 99. What does this code show?

```jsx
const App = () => {
  const [show, setShow] = React.useState(true);

  React.useEffect(() => {
    setShow(false);
  }, []);

  return <div>{show ? "True" : "False"}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "False"
- B: Displays "True"
- C: Displays nothing
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets `show` to `false` after the initial render, so it displays "False".

</p>
</details>

---

###### 100. What will this code display?

```jsx
const App = () => {
  const [count, setCount] = React.useState(0);

  React.useEffect(() => {
    setCount((prev) => prev + 1);
  }, []);

  return <div>{count}</div>;
};

ReactDOM.render(<App />, document.getElementById('root'));
```

- A: Displays "1"
- B: Displays "0"
- C: Infinite loop
- D: Error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

The `useEffect` hook sets `count` to "1" after the initial render, so it displays "1".

</p>
</details>
