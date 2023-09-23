# Layout

## Root Layout

: 서버로부터 응답받는 initial HTML을 수정할 수 있게 해 줌

- defined at the top level of the app directory & applies to all routes
- app directory는 root layout을 무조건 가지고 있어야 함!
- root layout은 `html`, `body` 태그를 포함해야 하며 이 태그들은 root layout만이 가지고 있을 수 있음
- `head`는 Next.js의 `Metadata` object로 접근 & 수정 가능
- root layout은 기본적으로 서버 컴포넌트이며, 클라이언트 컴포넌트로 바꿀 수 없음
