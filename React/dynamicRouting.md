# Dynamic Routing

동적 경로란 특정 아이템을 나타내는 id처럼 값이 변하는 요소를 URL에 포함하는 경우를 말한다.<br>
예를 들어 일기 아이템의 id가 3인 상세 페이지의 URL을 “/diary/3” 또는 “/diary?id=3”과 같이 표현할 수 있다.<br>
동적 경로를 표현하는 방법에는 URL 파라미터와 쿼리 스트링 두 가지가 있다.

<br>

### URL 파라미터

URL에 유동적인 값을 넣는 방법이다. 값은 중괄호로 표기한다.<br>
특정 id를 포함한 상세 페이지의 URL은 "https://localhost:3000/diary/{id}"와 같이 표기한다.<br>
이 방식은 주로 id나 이름을 이용해 특정 데이터를 조회할 때 사용한다.<br>
react-router-dom을 사용해 Route를 설정할 때 URL 파라미터로 경로를 설정하고,<br>

```
<Routes>
    <Route path="/diary/:id" element={<Diary />} />
</Routes>
```

해당 페이지에서 react-router-dom이 제공하는 훅인 useParams를 사용해 URL 파라미터로 전달한 id를 불러와 사용한다.

```
// Diary.js
function Diary() {
    const { id } = useParams();
    return ...
}
```

<br>

### 쿼리 스트링

물음표(?) 뒤에 key=value 문법으로 URL에 유동적인 값을 포함하는 방법이다.<br>
https://localhost:3000?sort=latest<br>
만약 URL에 유동적인 값을 두 개 이상 포함해야 한다면 &로 구분한다.<br>
https://localhost:3000?sort=latest&page=1<br>
보통 게시물 리스트에서 사용자가 정렬 조건을 선택하거나 현재 조회하는 게시판의 페이지를 표현할 때 사용한다.<br>
URL 경로 다음에 ?로 구분하므로 URL 파라미터처럼 페이지 라우팅을 위한 별도의 설정이 필요 없다.<br>
react-router-dom이 제공하는 useSearchParams 훅을 이용하면 쿼리 스트링 값을 꺼내 사용할 수 있다.

```
function Home() {
  const [searchParams, setSearchParams] = useSearchParams();
  console.log(searchParams.get("sort"));
  return <div>Home 페이지입니다.</div>;
}
```

이렇게 하고 localhost:3000?sort=latest로 접속하면 쿼리 스트링으로 설정한 sort 값이 콘솔에 출력된다. (이 예시에서는 latest가 콘솔에 출력된다.)

<br>

참고

- 한 입 크기로 잘라 먹는 리액트 - 이정환
