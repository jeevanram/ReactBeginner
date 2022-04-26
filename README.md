# ReactBeginner
Basic React Learning Path for beginners

Use Browser Sync to test the react learning htmls
npx browser-sync start --server --files "./*.html" --no-open --no-notify --directoryify --directory


References
----------

https://egghead.io/courses/the-beginner-s-guide-to-react


React Hooks ?
React Hooks are in-built functions that allows React developers to use state and lifecycle methods inside functional components.

3 RULES
1) Hooks can be called inside React function components
2) Hooks cannot be conditional
3) Hooks can only be called at the top level of a component

UseState
1) useState - Hook us to track state in a function component.
2) Could create multiple state hooks to track different values
3) Two way data binding

UseEffect
1) Hook that helps us to handle operations that will affect your component and cannot be done during rendering.
For instance, fetching data, subscriptions or manual DOM manipulation(anything
done in the past)

useEffect causes side effects to functional component. For instnace, Helps to add and remove DOM listeners.

    Benefits
    1) Avoid duplication of code
    2) Bring related code together
    3) Separating effects by their purpose

    componentDidMount() {
        // Fetch data from API
    }
    componentDidUpdate(prevProps, prevState) {
        // Send data when props change
    }
    componentWillUnmount() {
        // Unsubscribe from events before the component is removed
    }

    --useEffect combines all three methods into one single API.

2) Triggered every time after first render and after every update

    Dependencies Array
    ------------------
    To avoid performance issues and run the useEffect only when necessary,
    use the dependent array parameter to specify the fields which when updated 
    will trigger the useEffect module

    [name] - Run on first render and only when name is updated
    [] - Run on first render

    Can use multiple effects
    ------------------------
    React.useEffect(() => {
        // Code to be called after the first render
    }, []);
    React.useEffect(() => {
        // Code to be called after every render
    });

3) useEffect Vs componentDidMount

    useEffect - This built-in function will run after react renders the component(runs asynchronously) and ensures that the effect callback does not block the browser painting. 
    This differs from the behavior in class components where 'componentDidMount' or 'componentDidUpdate' runs synchronously after rendering.

    However, if the effect code is changing the DOM  and the DOM change will change the appearance between the time that it is rendered and the effect code that mutates it. 

