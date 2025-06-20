# 📘 React 기본기 정리: 스스로 활용 가능한 수준을 위한 기초 개념 정리 (日本語対応版)

(중략 - 기존 내용 동일)

---

## 🧪 항목별 실습 예제 프로젝트（各セクションの練習用プロジェクト）

(중략 - 기본 실습 예제들)

---

## 🧩 고급 실습 예제（応用的な実装例）

### 🛰 외부 API 호출 및 useEffect 사용 예제（API取得）
- 목표: `https://jsonplaceholder.typicode.com/users`에서 사용자 데이터 가져오기
```jsx
import React, { useEffect, useState } from "react";

function UserList() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((res) => res.json())
      .then((data) => setUsers(data));
  }, []);

  return (
    <div>
      <h3>ユーザー一覧</h3>
      <ul>
        {users.map((user) => (
          <li key={user.id}>{user.name} ({user.email})</li>
        ))}
      </ul>
    </div>
  );
}
```

### 🗃 상태 공유 + 입력 폼 (Lifting State Up)
- 목표: 자식 컴포넌트에서 상위 컴포넌트의 상태 업데이트
```jsx
function App() {
  const [keyword, setKeyword] = useState("");
  return (
    <div>
      <SearchInput onSearch={setKeyword} />
      <p>検索語: {keyword}</p>
    </div>
  );
}

function SearchInput({ onSearch }) {
  return (
    <input
      onChange={(e) => onSearch(e.target.value)}
      placeholder="検索ワードを入力"
    />
  );
}
```

### 🧩 다중 조건 렌더링 & 상태 조건 UI
- 목표: 로그인 여부에 따라 UI 변경 + 로딩 처리 추가
```jsx
function LoginControl() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);
  const [loading, setLoading] = useState(false);

  const toggleLogin = () => {
    setLoading(true);
    setTimeout(() => {
      setIsLoggedIn(!isLoggedIn);
      setLoading(false);
    }, 1000);
  };

  if (loading) return <p>読み込み中...</p>;

  return (
    <div>
      {isLoggedIn ? <p>ようこそ！</p> : <p>ログインしてください</p>}
      <button onClick={toggleLogin}>
        {isLoggedIn ? "ログアウト" : "ログイン"}
      </button>
    </div>
  );
}
```

---

## 🎯 최종 목표（最終目標）

(생략 - 동일)

---

필요하다면 상태 관리 라이브러리(Recoil, Zustand), 라우팅, 폼 유효성 검사 같은 주제도 추가해줄 수 있어！
必要であれば、状態管理ライブラリやルーティング、フォームバリデーションなどもユティがサポートできるよ！
