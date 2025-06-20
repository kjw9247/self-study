# 📘 React 기본기 정리: 스스로 활용 가능한 수준을 위한 기초 개념 정리 (日本語対応版)

## ✅ 1. JavaScript 기본 문법 (React 전에 꼭 알아야 할 것)／React前に理解しておくべきJavaScriptの基本文法

### 🧱 변수와 상수（変数と定数）
```js
let age = 20;
const name = "Yuto";
```
- `let`, `const`는 블록 스코프（ブロックスコープ）
- `const`는 재할당 불가（再代入不可）

### 🔁 조건문과 반복문（条件文とループ）
```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}
```
- `for`, `while`, `map`, `filter` 등 반복 처리 문법 익히기

### 🧠 함수（関数）
```js
const greet = (name) => `こんにちは、${name}さん！`;
```
- 화살표 함수, 매개변수와 반환 이해

### 📦 객체 & 배열（オブジェクトと配列）
```js
const user = { name: "Hana", age: 25 };
const fruits = ["apple", "banana"];
```
- 구조 분해, 배열 메서드 (`map`, `filter`, `find`) 등

### 🔗 이벤트（イベント）
```js
document.querySelector("button").addEventListener("click", () => alert("clicked!"));
```
- DOM 이벤트 처리 기본 개념

---

## ✅ 2. React 필수 기본 개념（Reactの基本概念）

### 🌱 JSX
```jsx
const message = "Hello";
return <div>{message}</div>;
```
- HTML과 유사하지만 JavaScript 표현식 포함 가능

### 🧱 컴포넌트（コンポーネント）
```jsx
function Header() {
  return <h1>サイトのタイトル</h1>;
}
```
- UI 구성 단위로 함수형 작성, 각 기능별 파일로 분리

### 🔄 props (속성 전달)／プロップス
```jsx
function Greeting(props) {
  return <p>こんにちは、{props.name}さん！</p>;
}
```
- 부모 → 자식 데이터 전달, 읽기 전용

### ⚙️ state (상태 관리)／ステート
```jsx
const [count, setCount] = useState(0);
```
- 상태 저장 및 변경, 컴포넌트 재렌더링 유도

### 🧠 이벤트 핸들링（イベント処理）
```jsx
<button onClick={() => setCount(count + 1)}>+</button>
```
- `onClick`, `onChange` 등으로 사용자 입력 처리

---

## ✅ 3. 컴포넌트 구조화와 상태 흐름／コンポーネント構造と状態の流れ

### 📦 컴포넌트 분리（役割別）
```jsx
// Header.jsx
function Header() {
  return <header>ヘッダー</header>;
}
```
- 역할별 파일로 나누고 props로 연결

### 🔄 상태 흐름 정리（状態管理設計）
```jsx
function App() {
  const [title, setTitle] = useState("My App");
  return <Header title={title} />;
}
```
- 상위 → 하위로 상태와 변경 함수 전달

---

## ✅ 4. React에서 자주 쓰는 추가 개념（Reactの応用基礎）

### 📁 useEffect（副作用）
```jsx
useEffect(() => {
  console.log("初回レンダリング完了");
}, []);
```
- 렌더링 후 특정 작업 실행 (API 호출 등)

### 🛠 조건부 렌더링（条件付きレンダリング）
```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```
- 조건에 따라 출력할 요소 결정

### 📋 리스트 렌더링（配列描画）
```jsx
{fruits.map((item) => (
  <li key={item}>{item}</li>
))}
```
- 배열 데이터를 반복적으로 렌더링

---

## ✅ 5. 실전 적용 예시 요약（実践ポイントまとめ）

| 기술 요소 | 예시 | 적용 포인트 | 일본어 설명 |
|------------|------|---------------|----------------|
| JSX | `<div>{text}</div>` | 표현식 출력 | JSXはHTMLに似た構文で、JavaScript内で使用可能 |
| useState | `useState(0)` | 상태 정의 및 변경 | useStateで状態を定義し、更新可能 |
| props | `<Component prop="value" />` | 상위→하위 전달 | propsは親から子へデータを渡す手段 |
| 이벤트 | `onClick={handleClick}` | 사용자 이벤트 처리 | イベントハンドラでユーザー操作に反応 |
| map | `items.map()` | 배열 반복 렌더링 | 配列の要素を繰り返し描画する |

---

## ✅ 🎮 React를 이용한 가장 기본적인 구현 예시（Reactでの最も基本的な実装例）

### 🔘 카운터 앱 (기초 예제)
```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>カウント: {count}</h2>
      <button onClick={() => setCount(count + 1)}>+ 増やす</button>
      <button onClick={() => setCount(count - 1)}>- 減らす</button>
    </div>
  );
}

export default Counter;
```

- 버튼 클릭 시 상태(state) 변화
- JSX + useState + 이벤트 핸들링 + 함수형 컴포넌트 적용
- 일본어 UI 포함

---

## 🎯 최종 목표（最終目標）

- [ ] JSX 문법을 이해하고 HTML처럼 사용할 수 있다（JSX構文の理解）
- [ ] 컴포넌트를 나눠서 설계할 수 있다（役割別コンポーネント設計）
- [ ] props/state 개념을 이해하고 전달/변경할 수 있다（propsとstateの理解）
- [ ] 간단한 이벤트 처리, 조건 렌더링이 가능하다（イベント・条件処理）
- [ ] 상태 기반 UI 흐름을 설계할 수 있다（状態ベースのUI設計）

---

필요하다면 각 항목에 대해 예제 프로젝트 또는 실습 코드도 유티가 함께 만들어줄 수 있어！
必要であれば、それぞれの項目に対応する練習用コードやプロジェクトもユティが手伝うよ！
