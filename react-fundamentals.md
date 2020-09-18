### Remember

Answer these on your own, then compare answers as a group

1.  What is React?

A javascript library that gives developers tools to create apps.

2.  What is create-react-app?

create-react-app is a command that builds the boilerplate of react so that junior and mid-level developers don't have to.  It sets up our development enviroment so that we can actually run the app.

3.  What is Component Based Architecture?

It is how different parts of the page are layed out in react, and it makes it more reusable and easy to debug.  It encapsulates certain functionalities.

4.  What is JSX?

JSX is an extension of Javascript that allows it to display what is basically html elements, while still including javascript functionality.

5.  What is the virtual DOM?

A light-weight copy of the DOM, that react uses to make changes to the DOM when changes actually happen.  It doesn't have to reload the entire thing, which would really slow down performance.  This allows hot-reloading

6.  What is unidirectional (one-way) data flow?

Data in react flows from parent component to child component, and the only exception to this is through events.  We pass the data through props.

### Understand

Discuss these questions in pairs if you have a 4-person group

7.  Summarize what happens when you run `create-react-app my-app`

It creates the framework of a react app, and puts it in a folder called my-app.

8.  Explain what this code does:

```jsx
import React from "react";

const Mentor = props => (
  <div className="mentor-container">
    <h1 className={props.title === "Lead Mentor" ? "lead" : ""}>Tim Biles</h1>
    <ul>
      <li>Fort Worth, TX</li>
      <li>My email address is timbilestimbiles@gmail.com</li>
    </ul>
  </div>
);

export default Mentor;
```

It is importing the react package (line 40), creating a functional component called `Mentor`, and having that component display a div containing an h1 and a ul.  In the h1 component, it is using the props object passed in as an arguement to check if the title property of that object has a value of 'Lead Mentor'.  If it does, it sets the h1's className to be 'lead', and if it isn't, it sets the className to an empty string.  This component (Mentor), when displayed in another component will display the h1 containing `Tim Biles`, and the unordered list containing an address and a sentence.

9.  Explain how data is passed from a parent component to a child component.

The parent contains data, and hands it to its direct child component through where it is displaying that component, similarly to how you add properties to html tags.

### Apply

Try these on your own, but work together if you start to get stuck.

10.  Use `create-react-app` to create a new React application called `student-directory`

npm create-react-app student-directory

11.  Use the code from `Mentor` above to create a new functional, stateless component called `User` with a list of friends. Hard code the list of friends, do not use state or props.

```jsx
import React from 'react'

const User = () => (
  <div>
    <ul>
      <li> James </li>
      <li> Mallory </li>
      <li> Brandon </li>
    </ul>
  </div>
)

export default User
```

### Analyze, Evaluate, Create

Discuss these questions as a group

12. What are the benefits and drawbacks of using a tool like create-react-app?

13. Compare and contrast JSX with other templating options, such as those used in Angular or Vue

14. Compare and contrast one-way data flow with two-way data binding.
