# 📘 1단계: HTML & CSS 마스터 플랜

## 🎯 목표
- HTML과 CSS의 기본 구조 이해
- 시멘틱 마크업 능력 갖추기
- CSS 박스 모델, 포지셔닝, Flexbox, Grid 이해
- 감성 UI의 뼈대를 구성할 수 있는 수준까지

---

## 🧩 1. HTML 핵심 개념

### ✅ HTML 기본 구조
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>문서 제목</title>
</head>
<body>
  <h1>제목</h1>
  <p>문단입니다.</p>
</body>
</html>
```

### ✅ 시멘틱 태그
- `header`, `footer`, `main`, `section`, `article`, `nav`, `aside` 등
- 의미 있는 구조로 콘텐츠를 배치

### ✅ 폼 요소
- `input`, `select`, `textarea`, `button`, `label`, `form` 등

---

## 🎨 2. CSS 핵심 개념

### ✅ 선택자
- 기본: `태그`, `.클래스`, `#아이디`
- 결합: `div > p`, `ul li a`, `a:hover`

### ✅ 박스 모델
- `margin`, `border`, `padding`, `content`
- `box-sizing: border-box`

### ✅ 위치 지정
- `position: static / relative / absolute / fixed / sticky`
- `top`, `left`, `transform: translate()` 등 위치 제어

### ✅ 레이아웃
- `display: flex`
- `display: grid`

### ✅ 반응형 웹
- `@media screen and (max-width: 768px)` 등으로 브레이크포인트 설정

---

## 🌈 3. 감성 앱 디자인을 위한 추가 고려사항

### ✅ Tailwind CSS 도입
- 반복 스타일 제거, 일관된 디자인 유지
- 유틸리티 클래스 기반 빠른 개발
- CDN 버전으로 먼저 실습 후, React에서 통합 예정

```html
<!-- tailwindcdn -->
<script src="https://cdn.tailwindcss.com"></script>
```

---

## 🧠 연습 미션

1. **시멘틱 마크업으로 블로그 구조 만들기**
2. **Flexbox로 카드 레이아웃 구현하기**
3. **Grid로 갤러리 레이아웃 만들기**
4. **Tailwind로 감성 프로필 페이지 구성해보기**

---

## 🗂️ 다음 단계 예고: JavaScript 기초
- DOM 조작
- 이벤트 처리
- 동적 요소 생성 등으로 확장 예정

---

## 💡 예시 – 감성 텍스트 박스 스타일

```css
p {
  font-size: 16px;
  line-height: 1.5;
  color: #333;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 15px;
  margin: 20px auto;
  max-width: 600px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
```
