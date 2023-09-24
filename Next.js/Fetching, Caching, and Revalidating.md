# Fetching, Caching, and Revalidating

## Fetching Data on the Server with `fetch`

Next.js는 `fetch` web API를 확장해서 서버로의 각 요청마다 캐시 & revalidation을 설정할 수 있도록 함  
또한 React component tree를 렌더링하는 동안 `fetch` 요청을 자동으로 memoize하도록 함

```
// app/page.tsx

async function getData() {
  const res = await fetch('https://api.example.com/...')
  // The return value is *not* serialized
  // You can return Date, Map, Set, etc.

  if (!res.ok) {
    // This will activate the closest `error.js` Error Boundary
    throw new Error('Failed to fetch data')
  }

  return res.json()
}

export default async function Page() {
  const data = await getData()

  return <main></main>
}
```
