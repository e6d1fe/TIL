# Keeping Components Pure

**Pure functions only perform a calculation and nothing more.**

## Characteristics of a pure function

- **It minds its own business.** It should not change any objects or variables that existed before rendering.
- **Same inputs, same output.** Given the same inputs, a component should always return the same JSX.

```
function Cup({ guest }) {
  return <h2>Tea cup for guest #{guest}</h2>;
}

export default function TeaGathering() {
  let cups = [];
  for (let i = 1; i <= 12; i++) {
    cups.push(<Cup key={i} guest={i} />);
  }
  return cups;
}
```

⬆️ This one is fine because the `cups` array has just been created while rendering. However, it would be a problem if it were created outside the `TeaGathering` function because that would be changing a **preexisting** object.
