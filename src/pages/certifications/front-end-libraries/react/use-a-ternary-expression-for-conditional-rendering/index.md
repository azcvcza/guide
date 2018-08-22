---
title: Use a Ternary Expression for Conditional Rendering
---
## Use a Ternary Expression for Conditional Rendering

This is a stub. <a href='https://github.com/freecodecamp/guides/tree/master/src/pages/certifications/front-end-libraries/react/use-a-ternary-expression-for-conditional-rendering/index.md' target='_blank' rel='nofollow'>Help our community expand it</a>.

<a href='https://github.com/freecodecamp/guides/blob/master/README.md' target='_blank' rel='nofollow'>This quick style guide will help ensure your pull request gets accepted</a>.

<!-- The article goes here, in GitHub-flavored Markdown. Feel free to add YouTube videos, images, and CodePen/JSBin embeds  -->
const inputStyle = {
  width: 235,
  margin: 5
}

class CheckUserAge extends React.Component {
  constructor(props) {
    super(props);
    // change code below this line
    this.state = {
      input: '',
      userAge: ''
    }
    // change code above this line
    this.submit = this.submit.bind(this);
    this.handleChange = this.handleChange.bind(this);
  }
  handleChange(e) {
    this.setState({
      input: e.target.value,
      userAge: ''
    });
  }
  submit() {
    this.setState({
      userAge: this.state.input
    });
  }
  <!-- the full logic is that -->
  <!-- 1.render button1 -->
  <!-- 2.when button1 is clicked && input value != null -->
  <!-- 3. render button2 or button3 while button1 disappear -->
  
  render() {
    const buttonOne = !this.state.userAge?<button onClick={this.submit}>Submit</button>:"";
    const buttonTwo = (this.state.userAge && this.state.userAge>=18) ? <button>You May Enter</button> : "";
    const buttonThree = (this.state.userAge && this.state.userAge<18)? <button>You Shall Not Pass</button> :"";
    return (
      <div>
        <h3>Enter Your Age to Continue</h3>
        <input
          style={inputStyle}
          type="number"
          value={this.state.input}
          onChange={this.handleChange} /><br />
        {buttonOne}
        {buttonTwo}
        {buttonThree}
      </div>
    );
  }
};
