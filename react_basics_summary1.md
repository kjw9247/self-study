# 📘 React 기본기 정리: 스스로 활용 가능한 수준을 위한 기초 개념 정리 (日本語対応版)

## ✅ 1. JavaScript 기본 문법 (React 전에 꼭 알아야 할 것)／React前に理解しておくべきJavaScriptの基本文法

### 🧱 변수와 상수（変数と定数）
- `var`, `let`, `const`의 차이점 이해하기
  - `let`, `const`는 블록 스코프（ブロックスコープ）, `var`는 함수 스코프（関数スコープ）
  - `const`는 재할당 불가（再代入不可）

📌 예시（例）:
```js
let age = 20;
const name = "Yuto";
```

### 🔁 조건문과 반복문（条件文とループ）
- 조건문: `if`, `else`, `switch`
- 반복문: `for`, `while`, `forEach`, `map`, `filter`

📌 예시:
```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}
```

### 🧠 함수（関数）
- 선언식, 표현식, 화살표 함수 `=>` 사용
- 매개변수와 반환값

📌 예시:
```js
const greet = (name) => `こんにちは、${name}さん！`;
```

### 📦 객체 & 배열（オブジェクトと配列）
- 객체: `{ key: value }` 형태로 데이터 저장
- 배열: 순서가 있는 데이터 집합
- 메서드: `map`, `filter`, `find`, `push`, `includes`

📌 예시:
```js
const user = { name: "Hana", age: 25 };
const fruits = ["apple", "banana"];
```

### 🔗 이벤트（イベント）
- DOM 요소에 이벤트 연결: `addEventListener`
- React에서는 JSX 이벤트 속성 사용 (`onClick` 등)

---

## ✅ 2. React 필수 기본 개념（Reactの基本概念）

### 🌱 JSX
- HTML과 비슷한 문법을 JavaScript 안에서 사용
- 중괄호 `{}` 안에 표현식 사용 가능
- 하나의 부모 태그로 감싸야 함

📌 예시:
```jsx
const message = "Hello";
return <div>{message}</div>;
```

### 🧱 컴포넌트（コンポーネント）
- UI의 구성 요소. 함수형으로 주로 작성

📌 예시:
```jsx
function Header() {
  return <h1>サイトのタイトル</h1>;
}
```

### 🔄 props (속성 전달)／プロップス（親→子データ伝達）
- 부모 컴포넌트에서 자식 컴포넌트로 데이터 전달
- 읽기 전용

📌 예시:
```jsx
function Greeting(props) {
  return <p>こんにちは、{props.name}さん！</p>;
}
```

### ⚙️ state (상태 관리)／ステート（状態管理）
- 변화하는 데이터 관리용
- `useState()` 훅 사용

📌 예시:
```jsx
const [count, setCount] = useState(0);
```

### 🧠 이벤트 핸들링（イベント処理）
- 사용자 상호작용에 대응

📌 예시:
```jsx
<button onClick={() => setCount(count + 1)}>+</button>
```

---

## ✅ 3. 컴포넌트 구조화와 상태 흐름／コンポーネント構造と状態の流れ

### 📦 컴포넌트 분리（役割別にコンポーネント化）
- 재사용성과 유지보수성을 높이기 위해 컴포넌트를 분리

📌 예시:
```jsx
// Header.jsx
function Header() {
  return <header>ヘッダー</header>;
}
```

### 🔄 상태 흐름 정리（状態管理の設計）
- 상태는 가능한 공통 부모에서 관리하고, 필요한 하위 컴포넌트에 전달

📌 예시:
```jsx
<App>
  <Header title={title} />
</App>
```

---

## ✅ 4. React에서 자주 쓰는 추가 개념（Reactの応用基礎）

### 📁 useEffect（副作用処理）
- 컴포넌트 렌더링 시 실행되는 처리 (API 호출 등)

📌 예시:
```jsx
useEffect(() => {
  console.log("初回レンダリング完了");
}, []);
```

### 🛠 조건부 렌더링（条件付きレンダリング）
📌 예시:
```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

### 📋 리스트 렌더링（配列描画）
📌 예시:
```jsx
{fruits.map((item) => (
  <li key={item}>{item}</li>
))}
```

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

## 🎯 최종 목표（最終目標）

- [ ] JSX 문법을 이해하고 HTML처럼 사용할 수 있다（JSX構文の理解）
- [ ] 컴포넌트를 나눠서 설계할 수 있다（役割別コンポーネント設計）
- [ ] props/state 개념을 이해하고 전달/변경할 수 있다（propsとstateの理解）
- [ ] 간단한 이벤트 처리, 조건 렌더링이 가능하다（イベント・条件処理）
- [ ] 상태 기반 UI 흐름을 설계할 수 있다（状態ベースのUI設計）

---

필요하다면 각 항목에 대해 예제 프로젝트 또는 실습 코드도 유티가 함께 만들어줄 수 있어！
必要であれば、それぞれの項目に対応する練習用コードやプロジェクトもユティが手伝うよ！
