---
layout: post
title:      "React (fetch vs axios)"
date:       2020-10-10 16:49:16 +0000
permalink:  react_fetch_vs_axios
---


Both fetch and axios are used to make a request to an api to get back some data from them. Although they are similiar, axios is the more advanced way of making requests to an api. I would say that the biggest difference between the two is that you get a Json response in axios, however, with fetch, you have to convert the data to Json.

**Axios**

Axios is a 3rd party package that needs to be imported whenever you are going to use it on the component you will make the axios request on. You would need to install it first in the terminal with: npm install axios. Afterwards...

```
import axios from 'axios'
```

Here is an example of axios in action. In this example, we are going to go for a get request. We are going to use a fake link here so it won't work if you are trying it on your computer, you would have to get a real api url in order for it to work.

```
axios.get('https://api.linkedin.com/users')
     .then(response => {
		      this.setState({ users: response.data })
		 }
```

This axios request makes a get request to this url and pulls in data that is already in json and we call it response (doesn't have to be called response). We then pass the response into this.setState (assuming we are working with a class component) and fill in the users array with response.data (assuming response.data holds all the instances for the users). This is a very basic example of how we can use axios to get data from an api.





**Fetch**

Fetch is also a great way to make requests to an api. I used fetch at my time at Flatiron School and thought that it was a great and simple way to get data from an api. Fetch is a function that is built into modern browsers, which differs from axios, seeing as its a 3rd party package. As mentioned earlier, when getting data back from an api using fetch, you would need to Jsonify that data, unlike axios where the data is already in Json.

Here is an example of fetch in action:

```
fetch('https://api.linkedin.com/users')
      .then(response => response.json())
			.then(data => console.log(data))
```

In this example, we are requesting data from the url specified, specifically the users. With the .then syntax, we receive the response from the api, hence calling it response. We could have called it resp, or anything else but I went with response since thats they generally call it. After taking in the response, we then turn that response into json with response.json(). We then move forward with another .then, where we receive the data in json format, hence calling it data. We then console.log(data) to see the data in our console. We don't have to console.log the data but I prefer to do that first in order to assess the data and then decide what to do once I confirm that i am getting the data that I want from the fetch request.







