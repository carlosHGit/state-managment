## useStateHooks

before we start talking about hooks there are two important rules about hooks that react wants you to know:

# Rule 1: Only call Hooks at the top level

<a href="https://es.reactjs.org/docs/hooks-overview.html">From the official React documentation:</a>

"Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use
Hooks at the top level of your React function. By following this rule, you ensure that
Hooks are called in the same order each time a component renders. That's what allows
React to correctly preserve the state of Hooks between multiple useState and useEffect
calls."

# Rule 2: Only call Hooks from React Functions

<a href="https://es.reactjs.org/docs/hooks-overview.html">From the official React documentation:</a>

"Don't call Hooks from regular JavaScript functions. Instead, you can:
Call Hooks from React function components.
Call Hooks from custom Hooks (we'll learn about them on the next
page).
By following this rule, you ensure that all stateful logic in a component is clearly visible
from its source code."

# useState Hook

When we go from a stateless component to a simple statefull component, we can start by using the useState hook, a hook  provides us with a state and a function to update it.

the syntax is simple, and although it is not a straitjacket it is recommended to initialize it as follows
`const [count, setCount] = useState(0);`
in this particular case, the `count` is initialized to 0, but state could also be a string, an array, an object, etc...
the `setCount` will be the only method by which we can update the value of `count` state, example:
To increment by 1:
`setCount(count + 1)`
to decrement by 1
`setCount(count + 1)`
and to bring the state to a value said
`setCount(10)`

Now a practical example of the use of this hook
<a href="https://github.com/carlosHGit/use-state-counter">use-state-counter project</a>.