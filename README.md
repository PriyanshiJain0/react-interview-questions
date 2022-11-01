# React Interview Questions

|Sl.No| Questions                                                                         |
|-----|-----------------------------------------------------------------------------------|
|     |[Explain Code Splitting and How do you achive it?]()|
|     |[What are the major features of React?](#q-what-are-the-major-features-of-react)|
|     |[Why did you choose React over Angular or anyother library?](#q-why-did-you-choose-react-over-angular-or-anyother-library)|
|     |[How do you create and run a project in React?](#q-how-do-you-create-and-run-a-project-in-react)|
|     |[Explain package.json and package-lock.json file?](#q-explain-packagejson-and-package-lockjson-file)|
|     |[What makes DOM manipulation slow?]()|
|     |[What is VDOM and What is Reconciliation?]()|
|     |[How does Virtual DOM works?]()|
|     |[How do you pass event from onClick handler in react to stop propagation?](#q-how-do-you-pass-event-from-onclick-handler-in-react-to-stop-propagation)|
|     |[What are React Hooks?](#q-what-are-react-hooks)|
|     |[Explain useState hook?](#q-explain-usestate-hook)|
|     |[Is setState synchronous or asynchronous?](#q-is-setstate-synchronous-or-asynchronous)|
|     |[Where do you prefer to use component state using useState ?](#q-where-do-you-prefer-to-use-component-state-using-usestate-)|
|     |[What is the difference between state and props?](#q-what-is-the-difference-between-state-and-props)|
|     |[Why should we not update the state directly?](#q-why-should-we-not-update-the-state-directly)|
|     |[Can you update the props?](#q-can-you-update-the-props)|
|     |[What is lifting state up?](#q-what-is-lifting-state-up)|
|     |[How do you pass data between parent and child component?](#q-how-do-you-pass-data-between-parent-and-child-component)|
|     |[What is "key" prop and what is the benefit of using it in arrays of elements?](#q-what-is-key-prop-and-what-is-the-benefit-of-using-it-in-arrays-of-elements)|
|     |[What is the impact of indexes as keys?](#q-what-is-the-impact-of-indexes-as-keys)|
|     |[What are controlled and uncontrolled components in react?](#q-what-are-controlled-and-uncontrolled-components-in-react)|
|     |[How do you write uncontrolled component using useRef hook?](#q-how-do-you-write-uncontrolled-component-using-useref-hook)|
|     |[What are stateful and stateless (presentational) components?](#q-what-are-stateful-and-stateless-presentational-components)|
|     |[What is useEffect Hook and its usage?](#q-what-is-useeffect-hook-and-its-usage)|
|     |[How do you track component Mount, Render, Re-Render and Unmount ? or What is the lifecycle of a React Component?](#q-how-do-you-track-component-mount-render-re-render-and-unmount--or-what-is-the-lifecycle-of-a-react-component)|
|     |[Explain React.Memo](#q-explain-reactmemo)|
|     |[How to do custom equality check using React.memo?](#q-how-to-do-custom-equality-check-using-reactmemo)|
|     |[(useCallback) What if you are passing callback function as prop, how does memo work and how to fix that issue ?](#q-what-if-you-are-passing-callback-function-as-prop-how-does-memo-work-and-how-to-fix-that-issue-)|
|     |[How do you handle if the loading time of your app is increasing ?](#q-how-do-you-handle-if-the-loading-time-of-your-app-is-increasing-)|
|     |[Explain Error Boundaries in react](#q-explain-error-boundaries-in-react)|
|     |[Explain useMemo Hook?](#q-explain-usememo-hook)|
|     |[Explain Context API with steps](#q-explain-context-api)|
| N   |[What do you do to maintain the logs in your app?]()|
| N   |[What is HOC and How do you write your own HOC?]()|
| N   |[What is Props Proxy ?]()|
| N   |[What is useReducer hook?]()|
| N   |[How does authentication work in your application?]()|
| N   |[Shadow DOM and Virtual DOM]()|
| N   |[Synthetic and Native Events]()|
| N   |[How does JSX is converted to JS ES5]()|
| N   |[What is Webpack and Babel]()|
| N   |[Overview of Charts]()|
| N   |[Infrastrture needed to host an app]()|
| N   |[How to include typegrapy in your app]()|
| N   |[How does your project directory structure look like?]()|
| N   |[Overview of material UI]()|
| N   |[Overview of lodash library]()|
|     |**React Router**|
|     |[How do you configure routing on react app?](#q-how-do-you-configure-routing-on-react-app)|
|     |[What are hooks available in React Router?](#q-what-are-hooks-available-in-react-router)|
|     |[What are links in React Router?](#q-what-are-links-in-react-router)|
|     |**Redux**|
|     |[What is redux ?](#q-what-is-redux-)|
|     |[Why should we use redux in our application?](#q-why-should-we-use-redux-in-our-application)|
|     |[Redux and Redux Toolkit Steps](#q-redux-and-redux-toolkit-steps)|
| N   |[Redux Saga Steps](#q-redux-saga-steps)|
| N   |[What is a reducer function and why it is pure function?]()|
| N   |[How does component automatically rerenders when store changes?]()|
| N   |[How does dispatch works behind the scene?]()|
| N   |[What is the difference between redux thunk and redux saga]()|
| N   |[How can you make your react app performant?]()|
|     |**Legacy React**|
|     |[Explain component lifecycle in case of classes](#q-explain-component-lifecycle-in-case-of-classes)|
|     |**Typescript-React**|
| N   |[Why did you choose TypeScript over Javascript in React App building?](#q-why-did-you-choose-typescript-over-javascript-in-react-app-building)|
| N   |[What is the difference between types and interface ?](#q-what-is-the-difference-between-types-and-interface-)|
|     |**Unit Testing**|
| N   |[Shallow Rendering ]()|
| N   |[What is dependecy injection]()|
| N   |[getByText and some otehr functions used in testing]()|

### Q. What is the difference between React.createElement and React.cloneElement ?

The **React.createElement()** method is used to create elements. Whenever we write code in JSX , JSX converts it to React.createElement(). The createElement method is not recommended to use as it is very hard to maintain or debug. We’ve to call the React.createElement() method every time for the creation of a React element, even if it is just a span tag with no attributes.

```js
React.createElement(
    type,
    [props],
    [...children]
)
```

```js

import React from 'react';
import "./styles.css";
const title = React.createElement('h1', 
    {className:'title'}, 'GeeksforGeeks');
const App =()=>
  React.createElement('div', {}, [
    React.createElement('button',{className:'btn'}, title),
    React.createElement('button', {className:'btn'}, title),
]);
  
export default App;
```

### Q. Explain React.strictMode ?

React.strict mode is a sort of a helper component that will help you to write better components.

```js
ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

1. Strict mode verifies that the components are following some of the recommended practices and warn you in the console
2. It verifies that the deprecated methods are not being used, and if they are used then it will warn you on the console.
3. It is just used for development purpose and does not impact the production build.
4. It is useful to identify the unsafe, legacy and deprecated API used in the application.
5. It renders every component in the app twice to identify the problems just for development environment only.

### Q. Explain Custom Hooks ?

Custom hooks lets you extract component logic into reusable components. Suppose you have a logic which has to be share amoung multiple components then that logic can be moved to custom hook.

Use cases: Debouncing, Throttling.

A custom hook is a javascript function whose name starts with `use`.

`useFetch` custom hook

```js
import { useEffect, useState } from "react";

const useFetch = (URL: string = "", options: any = null) => {
  const [data, setData] = useState(null);
  const [error, setError] = useState(null);
  const [isLoading, setIsLoading] = useState(false);

  useEffect(() => {
    setIsLoading(true);
    fetch(URL, options)
      .then((res) => {
        return res.json();
      })
      .then((data) => {
        setData(data);
        setError(null);
      })
      .catch((err) => {
        setError(err);
        setData(null);
      })
      .finally(() => {
        setIsLoading(false);
      });
  }, [URL, options]);

  return { data, error, isLoading };
};

export default useFetch;
```


### Q. Explain Code Splitting and How do you achive it?

React application bundled their files using tools like `Webpack` and `Browserfy`. Bundling is a process which takes multiple files and merges them into a single file, which is called a bundle. The bundle is responsible for loading an entire web app at once on the browser.

As your app grows, our bundle will grow too, especially when we are using thrid party libraries like `chartjs`, `react-simple-maps` etc. If the bundle size gets large, it will take some time to load on the webpage. So, it is better to split the code among multiple bundles and load them when needed.

React 16.6.0 introduced a way to do code splitting. Code Splitting is a feature supported by Webpack and Browserfy, which can create multiple bundles that can be dynamically loaded at runtime.

Code-Splitting uses `React.lazy` and `Suspense`, which helps your to load dependency lazily and only load it when needed by the user.

The code splitting improves:

- The performance of the app
- The impact on memory

**`Route based code splitting`**
```js
import { Switch, BrowserRouter as Router, Route} from 'react-router-dom';  
import React, { Suspense, lazy } from 'react';  
  
const Home = lazy(() => import('./routes/Home'));  
const About = lazy(() => import('./routes/About'));  
const Contact = lazy(() => import('./routes/Contact'));  
  
const App = () => (  
  <Router>  
    <Suspense fallback={<div>Loading...</div>}>  
      <Switch>  
        <Route exact path="/" component={Home}/>  
        <Route path="/about" component={About}/>  
        <Route path="/contact" component={Contact}/>  
      </Switch>  
    </Suspense>  
  </Router>  
);  
```

### Q. How do you handle if the loading time of your app is increasing ?

We can handle it using `React-Lazy` Loading.

**React.lazy** takes a function that must call a dynamic import(). This must return a Promise which resolves to a module with a default export containing a React component.
The lazy component should then be rendered inside a Suspense component, which allows us to show some fallback content (such as a loading indicator) while we’re waiting for the lazy component to load.

The fallback prop accepts any React elements that you want to render while waiting for the component to load. You can place the Suspense component anywhere above the lazy component. You can even wrap multiple lazy components with a single Suspense component.

**Example:**
```js
import React, { Suspense } from 'react';

const OtherComponent = React.lazy(() => import('./OtherComponent'));

function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <OtherComponent />
      </Suspense>
    </div>
  );
}
```
**Example 2**
```js
import React, { Suspense } from 'react';

const OtherComponent = React.lazy(() => import('./OtherComponent'));
const AnotherComponent = React.lazy(() => import('./AnotherComponent'));

function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <section>
          <OtherComponent />
          <AnotherComponent />
        </section>
      </Suspense>
    </div>
  );
}
```

### Q. What are the major features of React?

The major features of React are: 

- It uses VirtualDOM instead of RealDOM considering that RealDOM manipulations are expensive.
- Follows Unidirectional* data flow or data binding.
- Uses reusable/composable UI components to develop the view.

### Q. Why did you choose React over Angular or anyother library?

There are some of the reasons of choosing React over Angular:

- React just a library, the size of the library is smaller as compared to the whole framework
- React is quick and efficient
- React is better for component based UI structure
- React follows VDOM to update DOM where it uses diffing algorithm to compare previous and current VDOM and only the difference will be updated to DOM.
- React follows concept of batching in which batch of all the setStatements will be combined together and updated to DOM

### Q. How do you create, run and build a project in React?

- `Node` must be installed on the system
- A package manager, `npm` automatically installs with the installation of Node

- Install create-react-app package using npm command
```js
npm install -g create-react-app
```

- Create project using create-react-app
```js
create-react-app test-app --template typescript
```

- `Run Project in local development server`
```js
npm run start
```

- `Generate production optimized build`
```js
npm run build --prod
```

### Q. Explain package.json and package-lock.json file?

**`package.json`** is used to store the metadata associated with the project as well as to store the list of dependency packages.

- lists the packages your project depends on
- specifies versions of a package that your project can use
- makes your build reproducible, and therefore easier to share with other developers

<p align="center">
  <img src="https://user-images.githubusercontent.com/50094184/138094627-a6b5b6de-d455-45d3-99bc-0ff1fe30b769.png" width="60%" />
</p>

**`package-lock.json`** is automatically generated for any operations where npm modifies either the node_modules tree, or package.json.

### Q. What makes DOM manipulation slow?

The DOM is represented as a tree data structure. Because of that, the changes and updates to the DOM are fast. But after the change, the updated element and it’s children have to be re-rendered to update the application UI. The re-rendering or re-painting of the UI is what makes it slow. Therefore, the more UI components you have, the more expensive the DOM updates could be, since they would need to be re-rendered for every DOM update.

### Q. What is VDOM and What is Reconciliation?

In simple words, Virtual DOM is just a copy of original DOM kept in the memory and synced with the real DOM by library such as ReactDOM.

VDOM has the same properties as that of the real DOM. Reconciliation is a process through with react updates the DOM.

### Q. How does Virtual DOM works?

When a state is changed in the component using setState, React creates a new VDOM tree and update the VDOM with the changes.

So when there is an update in the virtual DOM, react compares the virtual DOM with a snapshot of the virtual DOM take right before the update of the virtual DOM.

With the help of the diffing algorithm, React figures out which component in the UI needs to be updated. Then it replaces the original DOM nodes with the updated DOM node.

React maintains two copies of Virtual DOM, one with updated state Virtual DOM and other with previous state Virtual DOM.

Once React has figured out the component which needs to be changed after multiple set states, it executes all the changes in one event loop, and in one bulk update repaints the real DOM. This means only one time repainting will happen at the browser level.

<p align="center">
  <img src="https://user-images.githubusercontent.com/50094184/144723088-3c91fb41-5322-4163-82b6-a978be4e0f75.png" width="60%" />
</p>

The red circles represent the nodes that have changed. These nodes represent the UI elements that have had their state changed. The difference between the previous version of the virtual DOM tree and the current virtual DOM tree is then calculated. The whole parent subtree then gets re-rendered to give the updated UI. This updated tree is then batch updated to the real DOM.

### Q. How do you pass event and extra data from onClick handler in react to stop propagation?

```js
import React from "react";

const Login: React.FC = () => {
  const handleSubmit = () => {
    console.log("Submit clicked");
  };

  const handleSubmitWithEvent = (e: React.MouseEvent<HTMLButtonElement>) => {
    e.stopPropagation();
    console.log("Submit Clicked with Event");
  };

  const handleSubmitWithEventAndData = (
    e: React.MouseEvent<HTMLButtonElement>,
    fullName: string
  ) => {
    e.preventDefault();
    e.stopPropagation();

    console.log("Full Name: ", fullName);
  };

  return (
    <>
      <button onClick={handleSubmit}>Submit Without Event</button>
      <button onClick={handleSubmitWithEvent}>Submit With Event</button>
      <button onClick={(e) => handleSubmitWithEventAndData(e, "Harman")}>
        Submit With Event and Data
      </button>
    </>
  );
};

export default Login;
```

### Q. What are React Hooks?

- Hooks are functions that let you `hook into` React state and lifecycle features from function components. 
- Hooks don’t work inside classes – hooks let you use react without classes. 
- React provides a few built-in hooks like `useState`, `useEffect`, `useRef`, `useMemo`, `useContext`, `useCallback`, `useDispatch`, `useSelector`

**Rules of Hooks:** 
1. Only call Hooks at the top level – don't call Hooks inside loop, conditions, or nested functions. This ensures that hooks will be called in the same order on ever render. 
2. Only call Hooks from React function components – Don't call Hooks from regular Javascript functions (But from custom hooks we can call)

### Q. Explain useState hook?

The **`useState()`** is a Hook that allows you to have state variables in functional components. The `useState` hook is a special function that takes the initial state as an argument and returns an array of two entries. It returns a pair of values: the current state and a function that updates it. Each piece of state holds a single value, which can be an object, an array, a boolean, or any other type you can imagine.

**`Importing State from React`**
```js
import React, { useState } from 'react';
```

The useState Hook allows you to declare `only one state variable` (of any type) at a time, like this:
```js
const [showLogout, setShowLogout] = useState<boolean>(false);
const [name, setName] = useState<string>('John Cena');
const [usersList, setUsersList] = useState<Users[]>([]);
```

In subsequent renders (due to a change of state in the component or a parent component), the argument of the useState Hook will be ignored and the current value will be retrieved.

**`Setting State Variable`**
State variables can be updated with the special method provided by useState hook while declaring state. Here,

```js
const [showLogout, setShowLogout] = useState<boolean>(false);
const [name, setName] = useState<string>('John Cena');

const handleSubmit = () => {
  setShowLogout(true);
  setName('Harman');
}

<button onClick={handleSubmit}>Submit</button>
```

**Note:** Setting state variable will trigger rerender. Here, we are triggering the setState from the event handler so react will make a batch of both of the statements and trigger a single update to VDOM and then trigger single rerender to the component instead of two.

### Q. Is setState synchronous or asynchronous?

setState and useState both are asynchronous operations in react. React will make a batch of all set states inside the handler and make a single update to DOM from vDOM based on the diffing.

You can't get the updated value of the state right after updating it:

```js
const handleSubmit = () => {
  setShowLogout(true);
  setName('Harman');
  
  console.log(showLogout);     // returns false
}
```

So, to track the values are updated with the latest, react provides another hook called `useEffect`.

### Q. Where do you prefer to use component state using useState ?
Component state using useState will be used when the state is being used inside the component and its child component. But, useState is invalid if we want to share the state among multiple components on the same tree level of the VDOM. 

To share state among multiple components, we can take leverage of React Context API and Redux.

### Q. What is the difference between state and props?

|State|Props|
|-----|-----|
|State changes are asynchronous|Props are read-only|
|State is mutable|Props are immutable|
|State holds information about the component|Props allows you to pass data from one component to another as arguments|
|State can not be accessed by child component|Props can be accessed by child component|
|State can be used for rendering dynamic content within the component|Props can be used to communicate data between the components|
|Defined using useState Hook|Can be passed to child component via arguments|

### Q. Why should we not update the state directly?

If you try to update the state directly then it won't re-render the component. Instead, use setUsername function just like below which schedules an update to the component state and re-renders the component.

```js
const [username, setUsername] = useState<string>('');

const handleUsername = (e: React.changeEvent<HTMLInputElement>) => {
  username = e.target.value;    // Wrong
  
  setUsername(e.target.value);  // Correct
}
```

### Q. Can you update the props?

No, you can not update the props directly. React allows all the child components to act like pure functions with respect to props. Props can not be updated we use them as it is. If props needed to be updated, child component has to emit an event using callback functions.

### Q. What is lifting state up?

Lifting state up means when you are passing data from Child component to Parent component. This can be achived using callback functions.

### Q. How do you pass data between parent and child component?

From parent component to child component, we can pass props to child.  

From child to parent, we can use callback function. Parent’s callback function will be passed to the child as props and in child we can call callback function by passing arguments.

### Q. What is "key" prop and what is the benefit of using it in arrays of elements?

A `key` is a special string attribute you should include when creating arrays of elements. Key prop helps React identify which items have changed, are added, or are removed.

Most often we use ID from our data as key:
```js
const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
)
```

When you don't have stable IDs for rendered items, you may use the item index as a key as a last resort:
```js
const todoItems = todos.map((todo, index) =>
  <li key={index}>
    {todo.text}
  </li>
)
```

**Note:**
- Using indexes for keys is **not recommended** if the order of items may change. This can **negatively** impact performance and may cause issues with component state.
- There will be a warning message in the console if the key prop is not present on list items.

### Q. What is the impact of indexes as keys?

Keys should be stable, predictable, and unique so that React can keep track of elements.

In the below code snippet each element's key will be based on ordering, rather than from the unique key from DB. This limits the optimizations that React can do.
```js
{todos.map((todo, index) =>
  <Todo
    {...todo}
    key={index}
  />
)}
```

If you use element data for unique key, assuming todo.id is unique to this list and stable, React would be able to reorder elements without needing to reevaluate them as much.
```js
{todos.map((todo) =>
  <Todo {...todo}
    key={todo.id} />
)}
```

### Q. What are controlled and uncontrolled components in react?

**Controlled component**:

In a controlled component, the value of the input element is controlled by React. We store the state of the input element using **`useState`** hook, and by using event-based callbacks, any changes made to the input element will be reflected in the state as well. When a user enters data inside the input element of a controlled component, `onChange` function gets triggered and inside the code we check whether the value entered is valid or invalid. If the value is valid, we change the state and re-render the input element with new value. 

When `state` is used as storing the value of the `form inputs` then it is said to be `controlled component`. 

**Uncontrolled component**

In an uncontrolled component, the value of the input element is handled by the DOM itself. We use **`useRef`** hook to access the value of the form inputs. Whenever the value of the input element is changed, event-based callbacks are not called. Basically, react does not perform any action when there are changes made to the input element. Which means when there is no re-render as this is not controlled by react component.

### Q. How do you write uncontrolled component using useRef hook?

```js
import React, { useRef } from "react";

const UserForm: React.FC = () => {
  const userNameRef = useRef<HTMLInputElement>(null);
  const emailRef = useRef<HTMLInputElement>(null);
  const deptRef = useRef<HTMLInputElement>(null);
  const salaryRef = useRef<HTMLInputElement>(null);

  const handleSubmitForm = () => {
      const userName = userNameRef.current;
      
  }

  return (
    <>
      <div>
        Username: <input type="text" ref={userNameRef} />
        <br />
        Email: <input type="text" ref={emailRef} />
        <br />
        Dept: <input type="text" ref={deptRef} />
        <br />
        Salary: <input type="text" ref={salaryRef} />
        <br />
        <button type="submit" onClick={handleSubmitForm}>Submit Form</button>
      </div>
    </>
  );
};

export default UserForm;
```

### Q. Explain forwardRef ?

`forwardRef` is a helper function in React which allows you to forward a component's ref to another component. This is useful when you are using reusable atom components like Input, TextArea etc.

Ex: There is `Input` component and we need to access the DOM element from the parent then in this case we will create a ref in the parent and will pass that to the Input component.

Main.tsx

```js
const Main: React.FC = () => {

  const inputRef = useRef<HTMLInputElement>(null);
  
   useEffect(() => {
    inputRef.current?.focus();
  }, [inputRef.current]);
  
    return (
      <Input type="text" ref={inputRef} />
    );
}
```

```js
import React, { FC, forwardRef, Ref } from "react";

type InputProps = {
  type: string;
  ref: Ref<HTMLInputElement>;
};

const Input: FC<InputProps> = forwardRef(
  ({ type }: InputProps, ref: Ref<HTMLInputElement>) => {
    return <input type={type} ref={ref} />;
  }
);

export default Input;

```

### Q. What are stateful and stateless (presentational) components?

Stateful components are those componets which are considered as containers where component state will be created using useState. The purpose of this component is the perform the manipulations and pass the state to the child components.

Stateless components are those components which are responsible for presentational purposes. It only accepts the props from the parent component where the actual state is defined. This component does not include any manipulations related to the data, its just meant for the display purpose.

### Q. What is useEffect Hook and its usage?

The `useEffect` hooks lets you perform side effects in the functional component. Data fetching, setting up a subscription, and manually changing the DOM in React components are all examples of side effects.

**`What does useEffect do?`** By using this Hook, you tell React that your component needs to do something after render. React will remember the function you passed, and call it later after performing the DOM updates.

**`Why is useEffect called inside a component?`** Placing useEffect inside the component lets us access the state variable (or any props) right from the effect. We don’t need a special API to read it — it’s already in the function scope. Hooks embrace JavaScript closures and avoid introducing React-specific APIs where JavaScript already provides a solution.

**`Does useEffect run after every render?`** Yes! By default, it runs both after the first render and after every update. Instead of thinking in terms of “mounting” and “updating”, you might find it easier to think that effects happen “after render”. React guarantees the DOM has been updated by the time it runs the effects. It can be restricted by adding dependencies to the effect.

This hook will run on ever re-render of the component.
```js
useEffect(() => {
  console.log("ReRendered);
});
```

```js
useEffect(() => {
  //Mount of component
  
  return () => {
    //Unmount of component
  }
}, []);
```

```js
useEffect(() => {
   //This hook will run when name will get changed
}, [name]);
```

```js
useEffect(() => {
   //This hook will run when anyone of the dependency changes
}, [name, age, dept]);
```

### Q. How do you track component Mount, Render, Re-Render and Unmount ? or What is the lifecycle of a React Component?

All the stages of the lifecycle of React Component can be tracked using useEffect hook. Below are the stages:

1. Mounting
2. Rendering
3. Re-Rendering
4. Unmounting

### Q. Explain React.Memo

To improve user interface performance, React offers higher-order component: `React.memo`. When `React.memo()` wraps a component, React `memorize` the rendered output of the wrapped component then skips unnecessary rendering. 

When a component is warpped under `React.memo`, React renders the component and memorize the component. Before the next render, if the new props are same as of the previous props then react reuses the memorized result and skipping the re-rendering of the component.

Memorize only the `presentational components` to get proper performance from the `React.memo()`. If you are memorizing the containers, then inspite of performance benefits a component can lead to bugs for not re-rendering. So, be careful in using `React.memo`.

**Example:**
```js
import React from "react";

type MovieProps = {
  title: string;
  releaseDate: string;
};

const Movie: React.FC<MovieProps> = ({ title, releaseDate }: MovieProps) => {
  return (
    <>
      {`Title: ${title}`}
      {`Release Date: ${releaseDate}`}
    </>
  );
};

export default React.memo(Movie);
```

### Q. How to do custom equality check using React.memo?

By default, memo does shallow comparison of the props.

To customize the props comparison you can use the second argument to indicate an equality check function:

```js
React.memo(Component, [areEqual(prevProps, nextProps)]);
```

`areEqual(prevProps, nextProps)` function must return `true` if `prevProps` and `nextProps` are equal.

```js
function moviePropsAreEqual(prevMovie, nextMovie) {
  return prevMovie.title === nextMovie.title
    && prevMovie.releaseDate === nextMovie.releaseDate;
}
const MemoizedMovie2 = React.memo(Movie, moviePropsAreEqual);
```

`moviePropsAreEqual()` function returns `true` if prev and next props are equal.

### Q. (useCallback) What if you are passing callback function as prop, how does memo work and how to fix that issue ?

A component that accepts a `callback` must be handled with care when applying memoization. The parent component could provide different `instances` of the callback function on every render:

```js
function MyApp({ store, cookies }) {
  return (
    <div className="main">
      <header>
        <MemoizedLogout
          username={store.username}
          onLogout={() => cookies.clear('session')}
        />
      </header>
      {store.content}
    </div>
  );
}
```

Even if provided with the same `username` value, `MemoizedLogout` renders every time because it receives `new instances` of `onLogout` callback.

Memoization is `broken`.

To fix it, onLogout prop must receive the `same` callback instance. Let's apply **`useCallback()`** to preserve the callback instance between renderings:

```js
const MemoizedLogout = React.memo(Logout);
function MyApp({ store, cookies }) {
  const onLogout = useCallback(
    () => cookies.clear('session'), 
    [cookies]
  );
  return (
    <div className="main">
      <header>
        <MemoizedLogout
          username={store.username}
          onLogout={onLogout}
        />
      </header>
      {store.content}
    </div>
  );
}
```

### Q. Explain useMemo Hook?

`useMemo` is used to memorize values. 

When you have a huge calculations performed on every render, this increases the load time for the component on render. **`useMemo`** will only re-compute the values when one of the dependencies has changed. This optimization helps to avoid expensive calculations on every render.

```js
function expensiveOperation(a, b){
  //Performe Expensive Operation
  
  return "Some Value";
}

const memorizedValue = useMemo(() => {
  return expensiveOperation(a, b);
}, [a, b])
```

Here, a and b are parameters to the function, so if one of the dependencies will change it recalculates the expensiveOperation again. If both of the params are same, then it will return the memorized value.

If no dependency array is provided, react will perform re-calculations on every render and returns new value.

### Q. Explain Error Boundaries in react

By default, whenever any javascript error occur in the react application it will break the UI and show the error on the screen. There should be a friendly way to handle this. A javascript error should not break the UI, to solve this issue React introduced Error Boundary in React 16.

**Error Boundaries**
Error Boundaries are React Component that catches Javascript errors anywhere in their child component tree, log errors and show fallback UI instead of the crashed screen. Error boundaries catch errors during rendering andin lifecycle methods. 

Error boundaries do not catch errors for:
- Event handlers
- Asynchronous code (e.g. setTimeout or requestAnimationFrame callbacks)
- Errors thrown in the error boundary itself (rather than its children)

```js
import React, { Component, ReactNode } from 'react';
import FallBack from './Fallback';

type Props = {
    children: ReactNode;
};

type State = {
    hasError: boolean;
};

type ErrorInfo = {
    componentStack: string;
};

export default class ErrorBoundary extends Component<Props, State> {
    state: State = {
        hasError: false
    };

    static getDerivedStateFromError(error: Error): State {
        return { hasError: true };
    }

    componentDidCatch(error: Error, info: ErrorInfo): void {
        console.log("Call Api to save error messages to track in future");
        //API Call can only be called in this method
        //This method is used to log error message
    }

    render() {
        if (this.state.hasError) {
            return <FallBack />;
        }
        return this.props.children;
    }
}

```

**getDerivedStateFromError()**:

The `getDerivedStateFromError()` method is invoked if some error occurs during the rendering phase of any lifecycle methods or any children components. This method is used to implement the `Error Boundaries` for the React application. It is called during the render phase, so side-effects are not permitted in this method. For side-effects, use `componentDidCatch()` instead. 

```js
static getDerivedStateFromError(error: Error): State {
  return { hasError: true };
}
```

**Wrap Error Boundary in App.tsx component**

```js
import ErrorBoundary from './common/components/ErrorBoundary';

const App: React.FC = () => {
  return (
  <ErrorBoundary>
    //APP COMPONENT RENDERING PART 
  </ErrorBoundary>
)
}
```

### Q. Explain Context API.
Context API is a new feature added in React 16.3 that allows to share state across the entire app lightly with ease. It helps in assisting props-drilling from all the levels of your application.

The React Context API allows you to have central store where your data lives (just like Redux). The store can be inserted into any component directly.

**How it works?**

`React.createContext` is what all you need. It returns a `consumer` and a `provider`. 

**Provider** is a component that as its name suggests provides the state to its children. It will hold the store and be the parent of all the components that might need that store.

**Consumer** is a component that as its name suggests that consume and uses the state.

**1. Initialize the Context**
First, we need to create the context, which we can later use to create providers and consumers.

**common/contexts/user-context.ts**
```js
import React from "react";

type UserContextType = {
    isAuthenticated: boolean;
}

const initialContextValue: UserContextType = {
    isAuthenticated: false
}

const UserContext = React.createContext(initialContextValue);

export default UserContext;
```

**2. Pass Context from GrandParentComponent (Provider)**
```js
import React, { FunctionComponent, useState } from "react";
import ParentComponent from "./ParentComponent/ParentComponent";
import UserContext from "../common/contexts/user-context";

type GrandParentComponentProps = {};

const GrandParentComponent: FunctionComponent<GrandParentComponentProps> =
  () => {
    const [userName, setUserName] = useState<string>();
    const [isAuth, setIsAuth] = useState<boolean>(false);

    const userNameChangeHandler = (e: React.ChangeEvent<HTMLInputElement>) => {
      setUserName(e.target.value);
    };

    const handleSubmit = () => {
      if (userName === "Harman") {
        setIsAuth(true);
      } else {
        setIsAuth(false);
      }
    };

    return (
      <UserContext.Provider value={{ isAuthenticated: isAuth }}>
        <input type="text" value={userName} onChange={userNameChangeHandler} />
        <br />
        <button onClick={handleSubmit}>Submit</button>
        <br />
        <ParentComponent />
      </UserContext.Provider>
    );
  };

export default GrandParentComponent;
```

**3. Consume Context In GrandParentComponent Childs Directly (Consumer)**
```js
import { FunctionComponent, useContext } from "react";
import UserContext from "../../../common/contexts/user-context";

interface ChildComponentProps {}

const ChildComponent: FunctionComponent<ChildComponentProps> = () => {
  const { isAuthenticated } = useContext(UserContext);

  return (
    <>
      Child Using Data:{" "}
      {isAuthenticated ? "Authenticated" : "Not Authenticated"}
    </>
  );
};

export default ChildComponent;
```

### Can Context API will replae Redux ?

No. Only components which are child of that component where context is defined can use the state. It can not be accessed by adjacent components on same level. Hence, Redux will be used in that scenario.



### Q. How do you configure routing on react app?

1. Choosing our router
2. Creating our routes
3. Navigating between routes using links

**`Installation`**

React Router is broken down into 3 packages: `react-router`, `react-router-dom` and `react-router-native`.

**`react-router`**: This package provides the core routing components and functions for React Router applications. 

**`react-router-dom` & `react-router-native`**: Both are environment specific packages and they re-exports all from `react-router`, so we don't need to install `react-router`.

```js
npm install --save react-router-dom
```

**Choosing Out Router**

When starting a new project, you need to determine which type of router to use. For browser based projects, there are `<BrowserRouter>` and `<HashRouter>` components. The `<BrowserRouter>` should be used when you have a server that will handle dynamic requests, while the `<HashRouter>` should be used for static websites.

**Setup App to Work With App**

index.tsx
```js
import BrowserRouter from 'react-router-dom';


ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```

`Creating Routes`
app.tsx
```js
import { Route, Switch } from "react-router-dom";

const App: FC = () => {
  return (
    <Switch>
      <Route exact path="/login" component={Login} />
      <Route exact path="/dashboard" component={Dashboard} />
      <Route exact path="/user" component={User} />
      <Route exact path="/user/:id" component={UserDetail} />
      
      <Route exact path="/pods/:id/content-management/obligations"
          render={(routeComponentProps: any) => (
              <PodContentManagement podId={routeComponentProps.match.params.id} />
          )}
      />
      
      <Route exact path="/" component={Dashboard} />
    </Switch>
  );
};
```

`<Route>`s can be created anywhere inside of the router, but often it makes sense to render them in the same place. You can use the `<Switch>` component to group `<Route>`s. The `<Switch>` will iterate over its children elements (the routes) and only render the first one that matches the current pathname.


### Q. What are hooks available in React Router?

React Router ships with a few hooks that let you access the state of the router and perform navigation from inside your components.

`useHistory`: The useHistory hook gives you access to the history instance that you may use to navigate.

```js
import { useHistory } from "react-router-dom";

const Comp: React.FC = () => ({
  let history = useHistory();

  function handleClick() {
    history.push("/home");
  }

  return (
    <button type="button" onClick={handleClick}>
      Go home
    </button>
  );
});
```

`useParams`: useParams returns an object of key/value pairs of URL parameters. Use it to access match.params of the current `<Route>`.
  
```js  
<Route exact path="/pods/:id/content-management/obligations"
          render={(routeComponentProps: any) => (
              <PodContentManagement podId={routeComponentProps.match.params.id} />
          )} />

import { useParams } from "react-router-dom";
  
const Comp: React.FC = () => ({
    const { id } = useParams();
  
  
    return <></>;
});
```

### Q. What are links in React Router?

Application needs a way to navigate between pages. If we were to create links using anchor elements, clicking on them would cause the whole page to reload. React Router provides a `<Link>` component to prevent that from happening. When clicking a `<Link>`, the URL will be updated and the rendered content will change without reloading the page.

```js
import { Link } from 'react-router-dom';

function Header() {
  return (
    <header>
      <nav>
        <ul>
          <li><Link to='/'>Home</Link></li>
          <li><Link to='/roster'>Roster</Link></li>
          <li><Link to='/schedule'>Schedule</Link></li>
        </ul>
      </nav>
    </header>
  );
}
```

`<Link>`s use the to prop to describe the location that they should navigate to. This can either be a string or a location object (containing a combination of pathname, search, hash, and state properties). When it is a string, it will be converted to a location object.

```js
<Link to={{ pathname: '/roster/7' }}>Player #7</Link>
```

### Q. What is redux ?

Redux is a preditable state container for Javascript Applications (React, Angular, Vue etc). It serves as a centralized store for state that needs to be used across your entire application, remembering that state can only be updated in predictable fashion.

- Preditable
- Centralized
- Flexible to work with any UI layer
- Very less in size (just 2KB)

### Q. When should we use Redux in application?

Redux helps you deal with shared state management, but like any tool, it has tradeoffs.

Redux is more useful when:

- You have large amounts of application state that are needed in many places in the app
- The app state is updated frequently over time
- The logic to update that state may be complex

Before using the redux, think which state can be moved to Redux based on the above scenarios.

### Q. Flow of React-Redux App

<p align="center">
  <img src="https://user-images.githubusercontent.com/50094184/144721872-a3031738-cb7e-4799-8bb2-10107fcbcccd.png" width="60%" />
</p>

### What is action ?

Actions are simple JavaScript objects. It has a `type` property which specifies the type of the action we are performing and optionally, can also have a `payload` property which is used to send some data to our redux store.

### What is reducer function ?

Reducers are the functions that determine the changes in application state and return the updated state. They take actions as the argument and update the state inside the store.



### Q. Redux and Redux Toolkit Steps

- **Step 1: Install package redux-toolkit and react-redux**
```js
npm install @reduxjs/toolkit react-redux
```

- **Step 2: Create Redux Store**

src/common/store/configure-store.ts
This will create empty store without any reducers.

Import the `configureStore` API from Redux Toolkit. We'll start by creating an empty Redux store, and exporting it:

```js
import { configureStore } from '@reduxjs/toolkit'
// ...

export const store = configureStore({
  reducer: {
  },
})

// Infer the `RootState` type from the store itself
export type RootState = ReturnType<typeof store.getState>
```
`configureStore`:  


- **Step 3: Link React App with Store (Provide the Redux Store to React)**

Once the store is created, we can make it available to our React components by putting a React-Redux `<Provider>` around our application in src/index.tsx 

```js
import React from 'react'
import ReactDOM from 'react-dom'
import './index.css'
import App from './App'
import { store } from '/common/store/configure-store'
import { Provider } from 'react-redux'

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
)
```

- **Step 4: Create a Redux State Slice**

Add a new file named src/features/counter/counterSlice.tsx. In that file, import the `createSlice` API from Redux Toolkit.

Creating a slice requires a string name to identify the slice, an initial state value, and one or more reducer functions to define how the state can be updated. Once a slice is created, we can export the generated Redux action creators and the reducer function for the whole slice.

```js
import { createSlice, PayloadAction } from '@reduxjs/toolkit'

export interface CounterState {
  value: number
}

const initialState: CounterState = {
  value: 0,
}

export const counterSlice = createSlice({
  name: 'counter',
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1
    },
    decrement: (state) => {
      state.value -= 1
    },
    incrementByAmount: (state, action: PayloadAction<number>) => {
      state.value += action.payload
    },
  },
})

// Action creators are generated for each case reducer function
export const counterActions = counterSlice.actions;

export const counterReducer = counterSlice.reducer;
```

- **Add Slice Reducers to the Store**

Next, we need to import the reducer function from the counter slice and add it to our store. 

```js
import { configureStore } from '@reduxjs/toolkit'
import { counterReducer } from '../features/counter/counterSlice'

export default configureStore({
  reducer: {
    counter: counterReducer,
  },
});

// Infer the `RootState` type from the store itself
export type RootState = ReturnType<typeof store.getState>
```

- **Use Redux State and Actions in React Components**

Now we can use the React-Redux hooks to let React components interact with the Redux store. We can read data from the store with `useSelector`, and dispatch actions using `useDispatch`.

```js
import React from 'react'
import { RootState } from '../../app/store'
import { useSelector, useDispatch } from 'react-redux'
import counterActions } from './counterSlice'

export function Counter() {
  const count = useSelector((state: RootState) => state.counter.value)
  const dispatch = useDispatch()

  return (
    <div>
      <div>
        <button aria-label="Increment value" onClick={() => dispatch(counterActions.increment())}>Increment</button>
        <span>{count}</span>
        <button aria-label="Decrement value" onClick={() => dispatch(counterActions.decrement())}>Decrement</button>
      </div>
    </div>
  )
}
```

### Q. Redux Saga Steps

- **Install `redux-saga` package**
```js
npm install redux-saga
```

- **Create 3 reducer functions for an API**
Example for getUserReposFromGithub
```js

```

- **Create saga file and export generator functions**
    - Create actual function (async operation)
    - Create watcher function - it watches for an action to dispatch from any component



- **Create root saga file and export all generator function**
- **Linking Saga to Store, In configure-store, import createSagaMiddleware from redux-saga**
- **Create saga middleware and apply middleware in the store**
- **Run Saga Middleware**


### Q. How can you make your react app performant?

- **Use React.Fragment to Avoid Adding Extra Nodes to the DOM**
- **Use production build**
- **Lazy Load components using React.lazy and React.Suspense**
- **Use React.Memo for Component memorization**
- **Virtualize a large list using react-window**
- **Throttling and Debouncing Event Action in JavaScript**
- **Avoid using index as key for map**
- **Avoiding props in Initial States**
- **Spreading props on DOM elements**
- **Avoid inline function in render**
- **In case of class, use PureComponent**

### Q. How do you implement shouldComponentUpdate in react hooks?

### Q. Explain component lifecycle in case of classes?

Mouting:
- constructor
- getDerivedStateFromProps
- render
- componentDidMount

Updating:
- getDerivedStateFromProps
- shouldComponentUpdate
- render
- getSnapshotBeforeUpdate
- componentDidUpdate

Unmounting:
- componentDidUnmount

### Explain the purpose of render() in ReactJS ?


React.js library has two components:
- Class components
- Functional Components

Class components uses render function. The ReactDOM.render() function takes two arguments, HTML code and an HTML element.

Purpose of render():

1. React renders HTML to the web page by using a function called render().
2. The purpose of the function is to display the specified HTML code inside the specified HTML element.
3. In the render() method, we can read props and state and return our JSX code to the root component of our app.
4. In the render() method, we cannot change the state, and we cannot cause side effects( such as making an HTTP request to the webserver).

### Typescript-React

### Q. Why did you choose TypeScript over Javascript in React App building?

### Q. What is the difference between types and interface ?
we can extend the interface but types cant

### Q. React testing library ?
https://www.freecodecamp.org/news/8-simple-steps-to-start-testing-react-apps-using-react-testing-library-and-jest/
