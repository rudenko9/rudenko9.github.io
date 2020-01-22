---
layout: post
title:      "React Redux Hooks"
date:       2020-01-22 00:52:07 +0000
permalink:  react_redux_hooks
---

Learning new material is always interesting and fascinating, but sometimes knowledge fades and we forget things we have learned, especially if the material was boring or unclear.

In terms of coding, the knowledge that I gained through the year, I can tell that it is very important to practice to code every day and to research if there anything new in the coding world, any new approach to coding anything that would make a code or a life of a coder better. I kept an eye on all my notes and course materials while I was writing my project. Actually, I learned even more while writing my project. I watched many videos and read several articles and forums with coding advice. While doing research for my last project at Flatiron school, I came across a very useful and handy Hooks. So, I decided not to pass it by and did extended research into this topic and decided to challenge myself and use these hooks in my project.

The Hooks let you use state and other React features without writing a class, it is a JavaScript functions that allow functional components to access state and life cycle methods. Hooks provide a more direct API to the React concepts you already know: props, state, context, refs, and lifecycle.
Which, I believe, it makes the code looking cleaner and easy to read more scalable.


The first hook i would like to talk about is useEffect():
useEffect()hook was created to handle React lifecycle in more easy and clean way in functional style and it serves the same purpose as:

• componentDidMount

• componentDidUpdate

• componentWillUpdate


Every time the component renders or is rendered the useEffect() get called. useEffect() accepts two arguments: the first one is a function() (side effect) and the second one is dependencies.
If we do not pass the second argument, the function will be called every time the current component updating.
By using this Hook, you tell React that your component needs to do something after render. React will remember the function you passed (we’ll refer to it as our “side effect”), and call it later after performing the DOM updates.
Does useEffect run after every render? Yes! By default, it runs both after the first render and after every update, instead of thinking in terms of “mounting” and “updating”, you might find it easier to think that effects happen “after render”.

* if second argument (depends) not exist:
side effect will be called each time

* if second argument (depends) empty array:
 side effect will be called only once after component rendered 
 
* if second argument (depends) array with some value:
 side effect will be called only when that value was updated


```

import React, {useEffect} from 'react;

function Example() {

useEffect(() => {

//Run! like go to get some data from API.

}, []);

return (

<div>

{/* do something with data.*}

</div>
);

}

```

useSelector() hook provided by react-redux package
Allows you to extract data from the Redux store state, using a selector function.
The selector is approximately equivalent to the mapStateToProps argument to connect conceptually.

useDispatch()This hook returns a reference to the dispatch function from the Redux store. You may use it to dispatch actions as needed.


```


const Example = () => {

const dispatch = useDispatch()
const info = useSelector(state => state.list.date);

const handleClick = () => {

dispatch(changeDate(new Date().toLocalString()));

}

return(

<button onClick={handleClick}> click for change</button>

)
};

export default Example;


```

There are many more hooks we can use, you can check them in react and redux hooks docs.



