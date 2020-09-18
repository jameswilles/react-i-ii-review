### Remember

Answer these on your own, then compare answers as a group

1.  What is state?

State is an object that is where a component stores data that it has to initialize.  Functional components don't have access to this object.

2.  Where do you set initial state?

In the constructor in your class component

3.  What method do you use to update state?

this.setState({ key: newValue })

### Understand

Discuss this question in pairs if you have a 4-person group

4.  Explain what's happening in this component.

```jsx
import React, { Component } from "react";

class LeadMentor extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: 0
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAnswered: this.state.questionsAnswered + 1 });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Tim Biles</h1>
      <h3>{this.state.questionsAnswered}</h3>
      <h3>questions answered today</h3>
      <button onClick={this.handleClick}>Increase Answers</button>
    </div>;
  }
}
```

This is the component called LeadMentor.  It is initializing a value in it's state object called `questionsAnswered` and giving it a value of 0.  It is binding the handleClick method to have a context of LeadMentor, and that method is increasing the value of `questionsAnswered` by 1 whenever a button is clicked.  The component is rendering an h1 (containing a name), an h3 (which is displaying the value of `questionsAnswered`), another h3 (displaying `questions answered today`), and the button that increases the value of questionsAnswered.

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Create a `Student` component that keeps track of the number of questions the student has asked, with a button that adds 1 to the total when it's clicked

```jsx

import React, {Component} from 'react'

export default class Student extends Component {
  constructor() {
    super()
    this.state = {
      questionsAsked: 0,
      input: '',
      questions: [],
    }
    this.handleClick = this.handleClick.bind(this)
    this.handleChange = this.handleChange.bind(this)
    this.addQuestion = this.addQuestion.bind(this)
  }

  handleClick() {
    this.setState({ questionsAsked: this.state.questionsAsked++})
  }

  handleChange(val) {
    this.setState({ input: val})
  }

  addQuestion() {
    this.setState({questions: [...this.state.questions, input]})
    this.setState({ input: ''})
  }

  render() {
    return(
      <div>
        <h1>{this.state.questionsAsked}</h1>
        <button onClick={this.handleClick}> Ask a Question </button>
        <input value={this.state.input} onChange={this.handleChange((e) => {e.target.value})} />
        <button onClick={this.addQuestion}> Add Question </button>
        <h1>{this.state.questions}</h1>
      </div>
    )
  }
}

```
6.  Now add a text input where the student can type in their questions with a button to add them to a list of questions that is displayed below the number of questions asked.

See Above

### Analyze, Evaluate, Create

Discuss these questions as a group

7.  Could your `Student` component be refactored into a functional component? Why or why not?

No, functional components don't have access to the state object.

8.  What are the pros and cons of using a class method for an event handler vs. using an arrow function inline?

9.  The render() method is called every time a component's state is updated. For a text input, that means the render method is called for every keypress. Why isn't this bad for performance?
