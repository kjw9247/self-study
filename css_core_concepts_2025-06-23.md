
# 🎨 CSS 핵심 개념 정리

---

## ✅ 선택자 (Selector)

CSS에서 선택자는 어떤 요소에 스타일을 적용할지를 지정합니다.

| 선택자 유형 | 예시 | 설명 |
|-------------|------|------|
| 태그 선택자 | `p`, `h1`, `div` | 해당 태그 전체에 적용 |
| 클래스 선택자 | `.title`, `.box` | class 속성이 일치하는 요소에 적용 |
| 아이디 선택자 | `#header`, `#main-content` | id 속성이 일치하는 하나의 요소에 적용 |
| 자식 선택자 | `div > p` | `div`의 직계 자식인 `p`에만 적용 |
| 후손 선택자 | `ul li a` | `ul` 안의 모든 `li` 안의 `a`에 적용 |
| 가상 클래스 | `a:hover`, `input:focus` | 요소의 특정 상태(hover, focus 등)에 적용 |

---

## ✅ 박스 모델 (Box Model)

모든 HTML 요소는 박스 형태로 구성됩니다.  
`content` → `padding` → `border` → `margin` 순서로 이루어집니다.

| 속성 | 설명 |
|------|------|
| `margin` | 요소 바깥 여백 |
| `border` | 테두리 |
| `padding` | 테두리 안쪽 여백 |
| `content` | 실제 콘텐츠 영역 |
| `box-sizing: border-box` | padding과 border를 width, height에 포함시킴 (디자인 시 많이 사용됨) |

---

## ✅ 위치 지정 (Positioning)

요소를 문서 흐름과 다르게 위치시키고 싶을 때 사용합니다.

| 값 | 설명 |
|-----|------|
| `static` | 기본값, 문서 흐름대로 배치됨 |
| `relative` | 기존 위치 기준으로 이동 가능 |
| `absolute` | 가장 가까운 `relative` 조상 기준으로 위치 |
| `fixed` | 화면(viewport)에 고정 |
| `sticky` | 스크롤 위치에 따라 고정 상태 전환 |

> 보통 `absolute`, `relative`, `fixed`는 레이아웃 커스터마이징에 자주 쓰입니다.

또한 `top`, `left`, `right`, `bottom`과 함께 위치를 조정하며  
`transform: translate(x, y)`를 쓰면 부드럽고 정확한 위치 조정 가능

---

## ✅ 레이아웃 (Layout)

| 방식 | 설명 | 특징 |
|------|------|------|
| `display: flex` | 1차원 정렬(가로 또는 세로) | 간단한 정렬, 가운데 정렬, 반응형에 유용 |
| `display: grid` | 2차원 레이아웃 (행+열) | 복잡한 레이아웃, 영역 기반 배치에 적합 |

---

## ✅ 반응형 웹 (Responsive Web Design)

다양한 화면 크기(모바일, 태블릿, 데스크탑 등)에 맞게 스타일을 다르게 적용할 수 있게 해줍니다.

```css
@media screen and (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

- `@media`는 특정 조건(screen 크기 등)일 때만 CSS를 적용합니다.
- `max-width: 768px`은 화면 너비가 768px 이하일 경우를 뜻합니다.
- 주로 **모바일 화면 기준 스타일 조정**에 사용됩니다.

---

## ✅ 요약

- 선택자는 **대상을 고르는 방법**
- 박스 모델은 **공간을 구성하는 원리**
- 포지셔닝은 **위치를 자유롭게 조정하는 도구**
- Flex & Grid는 **레이아웃의 두 축**
- 미디어 쿼리는 **디바이스에 따라 스타일을 다르게 적용하는 기술**
