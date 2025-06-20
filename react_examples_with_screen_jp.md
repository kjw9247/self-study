
# TodoList（やることリスト）

## ✅ 使い方（プロジェクトに組み込む方法）
1. `src/TodoList.jsx` に以下のコードを保存
2. `App.js` で `<TodoList />` を読み込んで使用

## 📄 コード

```jsx
// TodoList.jsx
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

```jsx
// App.js で使用する例
import React from 'react';
import TodoList from './TodoList';

function App() {
  return (
    <div className="App">
      <TodoList />
    </div>
  );
}

export default App;
```


---


# Counter（カウンター）

## ✅ 組み込み方法
- `src/Counter.jsx` に保存
- `App.js` で読み込み

## 📄 コード

```jsx
// Counter.jsx
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

```jsx
// App.js
import React from 'react';
import Counter from './Counter';

function App() {
  return (
    <div className="App">
      <Counter />
    </div>
  );
}

export default App;
```


---


# InputMirror（入力ミラー）

## ✅ 組み込み方法
- `src/InputMirror.jsx` に保存
- `App.js` で読み込み

## 📄 コード

```jsx
// InputMirror.jsx
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

```jsx
// App.js
import React from 'react';
import InputMirror from './InputMirror';

function App() {
  return (
    <div className="App">
      <InputMirror />
    </div>
  );
}

export default App;
```


---


# ToggleButton（トグルボタン）

## ✅ 組み込み方法
- `src/ToggleButton.jsx` に保存
- `App.js` で読み込み

## 📄 コード

```jsx
// ToggleButton.jsx
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

```jsx
// App.js
import React from 'react';
import ToggleButton from './ToggleButton';

function App() {
  return (
    <div className="App">
      <ToggleButton />
    </div>
  );
}

export default App;
```


---


# ColorChanger（背景色チェンジャー）

## ✅ 組み込み方法
- `src/ColorChanger.jsx` に保存
- `App.js` で読み込み

## 📄 コード

```jsx
// ColorChanger.jsx
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

```jsx
// App.js
import React from 'react';
import ColorChanger from './ColorChanger';

function App() {
  return (
    <div className="App">
      <ColorChanger />
    </div>
  );
}

export default App;
```
