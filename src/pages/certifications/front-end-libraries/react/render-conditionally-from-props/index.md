---
title: Render Conditionally from Props
---
## Render Conditionally from Props

This is a stub. <a href='https://github.com/freecodecamp/guides/tree/master/src/pages/certifications/front-end-libraries/react/render-conditionally-from-props/index.md' target='_blank' rel='nofollow'>Help our community expand it</a>.

<a href='https://github.com/freecodecamp/guides/blob/master/README.md' target='_blank' rel='nofollow'>This quick style guide will help ensure your pull request gets accepted</a>.

<!-- The article goes here, in GitHub-flavored Markdown. Feel free to add YouTube videos, images, and CodePen/JSBin embeds  -->
class Results extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    
    return (
      <h1>
      {
        /* change code here */
        this.props.fiftyFifty
      }
      </h1>
    )
  };
};

class GameOfChance extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 1
    }
    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({
      counter: this.state.counter+1 // change code here
    });
  }
  render() {
    let expression = Math.random()>0.5?"You Win!":"You Lose!"; // change code here
    return (
      <div>
        <button onClick={this.handleClick}>Play Again</button>
        { /* change code below this line */ }
        <Results fiftyFifty={expression}/>
        { /* change code above this line */ }
        <p>{'Turn: ' + this.state.counter}</p>
      </div>
    );
  }
};
