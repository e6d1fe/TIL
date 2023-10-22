# Event Propagation

Also called event bubbling.  
It describes situations where event handlers will also catch events from any children your component might have.  
For instance, your component may look like this:

```
export default function Toolbar() {
  return (
    <div className="Toolbar" onClick={() => {
      alert('You clicked on the toolbar!');
    }}>
      <button onClick={() => alert('Playing!')}>
        Play Movie
      </button>
      <button onClick={() => alert('Uploading!')}>
        Upload Image
      </button>
    </div>
  );
}
```

What do you think will happen when you click on the first `button`?  
➡️ You'll first get the `Playing!` alert, and then get the `You clicked on the toolbar!` alert.

## How do we stop event propagation?

To stop behaviors like this, we utilize the event object by calling `e.stopPropagation()`.

```
function Button({ onClick, children }) {
  return (
    <button onClick={e => {
      e.stopPropagation();
      onClick();
    }}>
      {children}
    </button>
  );
}

export default function Toolbar() {
  return (
    <div className="Toolbar" onClick={() => {
      alert('You clicked on the toolbar!');
    }}>
      <Button onClick={() => alert('Playing!')}>
        Play Movie
      </Button>
      <Button onClick={() => alert('Uploading!')}>
        Upload Image
      </Button>
    </div>
  );
}
```

Reference

- https://react.dev/learn/responding-to-events
