---
layout: post
title:      "React Lifecycles"
date:       2020-09-09 13:50:51 -0400
permalink:  react_lifecycles
---


React lifecycles has three phases in which you can influence and monitor your React component.

* Mounting
* Unmounting
* Updating

The way you utilize lifecycle methods will differ based on the type of React component that you are using. First, we will talk about the lifecycle methods that you can use in a Class Component. An example of a Class component:

```
import React from 'react'

class App extends React.Component {

render() {

     return {
		<div>App</div>
		 }
		 
}

export default Users
```

In a Class component, the render method is required. Lifecycle methods are optional and are only used whenever you need them as it can add complexity to your app. Lets talk about the order in which the lifecycle methods get called.

**constructor**

The Constructor method is the first one to get called. This is the place where you can set up your initial state and any other values.

**getDerivedStateToProps**

This lifecycle method gets called before the render method and after the constructor. Its main purpose is to update the components internal state when there is a change in props. 

**shouldComponentUpdate**

shouldComponentUpdate takes a look at the current state and props, as well as the new one and checks to see if we should keep going. This method gets executed before the render method.

**render**

This required method gets called after the constructor and getDerivedStateToProps if you included these optional methods in your component. It is in this phase where the HTML is being rendered to the DOM.

**componentDidMount**

componentDidMount gets called whenever the component is mounted. Its useful whenever you want to load data with a delayed execution.


Now for Functional components, you can't use any of the methods mentioned above. Those methods are only allowed for the Class type component. For functional components, we can use hooks. We are going to take a look at the functionality of the useState and useEffect hooks.

**useState**

You can integrate useState to your functional React component like this:

```
import React, { useState } from 'react'

const Demo = () => {

      return (
			    <div>App</div>
			)

}

export default Demo
```

Now, lets integrate two buttons. The + and - buttons, and then add the number 0. We are going to use useState to increment and decrement the value. Lets add the buttons first.

```
import React, { useState } from 'react'

const Demo = () => {

      return (
			    <div>
					
					   <p>0</p>
						 
						 <button>+</button>
						 
						 <button>-</button>
						 
					</div>
			)

}

export default Demo
```

Now lets add our useState above the return. 

```
import React, { useState } from 'react'

const Demo = () => {

    const [count, setCount] = useState(0)

    return (
        <div>

            <p>{count}</p>

            <button>+</button>

            <button>-</button>

        </div>
    )

}

export default Demo
```

Here we added: const [count, setCount] = useState(0)

adding the 0 inside the parenthesses in useState sets count to 0. So when we added {count} inside our p tag, it will show up as 0 in our browser. Now we need to add an action to our buttons so that our counter increments and decrements accordingly, this is where setCount comes in!

```
import React, { useState } from 'react'

const Demo = () => {

    const [count, setCount] = useState(0)

    return (
        <div>

            <p>{count}</p>

            <button onClick={() => setCount(count + 1)}>+</button>

            <button onClick={() => setCount(count - 1)}>-</button>

        </div>
    )

}

export default Demo
```

As you can see, we added setCount(count + 1) to increment our value onClick and setCount(count - 1) to decrement our value onClick. setCount's job is to update count, simple as that. This is just one way we can use useState and its my favorite hook to utilize. It is simple to use and easy to maintain.

We are now going to look at another hook for Functional components called useEffect. I see the use of this hook and immediately think of componentDidMount and componentDidUpdate. Let me show you why. First lets integrate it to our Demo app.

```
import React, { useState, useEffect } from 'react'

const Demo = () => {


    const [count, setCount] = useState(0)

    useEffect(() => {
        console.log("second");
    })
		
		const first = () => {
        console.log("first");
    }
	

    return (
        <div>

        <p>{count}</p>

        <button onClick={() => setCount(count + 1)}>+</button>

        <button onClick={() => setCount(count - 1)}>-</button>
						
			  <p>{first()}</p>

       </div>
    )

}

export default Demo
```

If we refresh the page with the given code, you will see that first comes up before second does. useEffect will execute after the component mounts. If you click on a button, which rerenders the component, thus triggering useEffect, you will see first will come before second in our console, telling us the same thing.

****Lifecycle Rules****

You can't use lifecycle rules within loops, conditional statements, or even nested functions.


**Conclusion**

I hope that the demonstration for these lifecycle methods were clear, and that you're now able to come up with many ways to use these lifecycle methods for your next React application!





