
# TodoList（やることリスト）

```jsx
import React, { useState } from 'react';

// TodoListコンポーネントを定義
function TodoList() {
  const [tasks, setTasks] = useState([]); // やることのリスト
  const [input, setInput] = useState(""); // 入力フォームの状態

  // 入力が変更されたときの処理
  const handleChange = (e) => {
    setInput(e.target.value);
  };

  // フォームが送信されたときの処理
  const handleSubmit = (e) => {
    e.preventDefault(); // ページの再読み込みを防ぐ
    if (input.trim() !== "") {
      setTasks([...tasks, input]); // 新しいタスクをリストに追加
      setInput(""); // 入力フォームをクリア
    }
  };

  return (
    <div>
      <h2>やることリスト</h2>
      <form onSubmit={handleSubmit}>
        <input value={input} onChange={handleChange} />
        <button type="submit">追加</button>
      </form>
      <ul>
        {tasks.map((task, index) => (
          <li key={index}>{task}</li> // タスクをリストで表示
        ))}
      </ul>
    </div>
  );
}

export default TodoList;
```


---


# Counter（カウンター）

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0); // 数値の状態を管理

  return (
    <div>
      <h2>カウント: {count}</h2>
      <button onClick={() => setCount(count + 1)}>増やす</button>
      <button onClick={() => setCount(count - 1)}>減らす</button>
    </div>
  );
}

export default Counter;
```


---


# InputMirror（入力ミラー）

```jsx
import React, { useState } from 'react';

function InputMirror() {
  const [text, setText] = useState(""); // 入力された文字列

  return (
    <div>
      <input
        value={text}
        onChange={(e) => setText(e.target.value)} // 入力を状態に反映
      />
      <p>あなたが入力したのは: {text}</p> {/* 入力された文字列を表示 */}
    </div>
  );
}

export default InputMirror;
```


---


# ToggleButton（トグルボタン）

```jsx
import React, { useState } from 'react';

function ToggleButton() {
  const [on, setOn] = useState(false); // 状態がオンかオフかを管理

  return (
    <div>
      <button onClick={() => setOn(!on)}>
        {on ? "ON" : "OFF"} // 状態に応じてテキストを変更
      </button>
    </div>
  );
}

export default ToggleButton;
```


---


# ColorChanger（背景色チェンジャー）

```jsx
import React, { useState } from 'react';

function ColorChanger() {
  const [color, setColor] = useState("white"); // 背景色の状態を管理

  return (
    <div style={{ backgroundColor: color, padding: "20px" }}>
      <h3>背景色を変えよう</h3>
      <button onClick={() => setColor("lightblue")}>水色</button>
      <button onClick={() => setColor("lightgreen")}>緑</button>
      <button onClick={() => setColor("lightpink")}>ピンク</button>
    </div>
  );
}

export default ColorChanger;
```
