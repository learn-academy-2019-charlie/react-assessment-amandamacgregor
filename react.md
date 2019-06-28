# React Assessments

Try your best to answer each question on your own before looking up the answer online. Once you're done writing your first answer, you can google the question and write the best answer you find.

 #### 1. Here is a list of pros and cons to using the React library to build your application -- but some of them are false. Remove the false statements from the list:

- **FALSE:React was created to be simple, so that even people with minimal code experience could use it and create Single Page Applications (SPAs)
- React is a modern, efficient answer to complex UI applications
- **FALSE:React is a full stack framework for modern web applications
- React is a flexible library that plays the role of V in an MVC framework

 
 #### 2. What are "smart"(logic) and "dumb"(display) components? Explain the difference and also add why we bother to make the distinction between them.
 
 
 //Your Answer
 Smart (logic) are components that change their state with methods, etc.
 Dumb (display) components just take in 'instructions' and follow those instructions based on which apply to them.  Sarah made a really good point here with the
    battleship game.  The square doesn't know anything about why or how it does things - it takes information, looks to see if that information matches something like
    the user click, and if so says "oh ok!  I'll change to that color then kthxbai!" until it's called on to make the same check again next turn.
 
 //Googled Answer
 Dumb components are also called ‘presentational’ components because their only responsibility is to present something to the DOM. Once that is done, the component is done with it. No keeping tabs on it, no checking in once in a while to see how things are going. Nope. Put the info on the page and move on.
The components themselves only have a render() method (they don’t need any others) and are often just Javascript functions. They don’t have internal state to manage. They wouldn’t know how to change the data they are presenting if they were asked. Ignorance is bliss.
 
 Smart components (or container components) on the other hand have a different responsibility. Because they have the burden of being smart, they are the ones that keep track of state and care about how the app works.
Using the container design pattern, the container components are separated from the presentational components and each handles their own side of things. The container components do the heavy lifting and pass the data down to the presentational components as props.
They are class-based components and have their own state defined in their constructor() functions.
 
#### 3. When we use "yarn add ..." in the terminal - what is yarn doing? And what file will always be automatically updated after we add a package with yarn?
 
 
 //Your Answer
 We're adding ..not packages, but something so the thing can actually launch as expected.  We need this for every instance.
 
 //Googled Answer
 yarn add is used to add all *dependencies* for a project. ... 
    These have been replaced by yarn add and yarn add --dev . For more information, see the yarn add documentation.
 
 
#### 5. There are three mistakes in this code that would cause it to break our application. Find the mistakes and fix them:

    import React, { Component } from 'react';

    class Recipes *1*extends Component*1*{
      constructor(props){
        super(props)
        this.state = {
          recipes: 
            {name: 'Meatballs'},
            {name: 'Mac & Cheese'}
      
        }
      }

      render() {
    
        return (
    
          let *2*{ recipes }*2* = this.state.recipes.map(function(recipe){
            return(
            *3*<div>*3*
              <li key={recipe.name}>{recipe.name}</li>
            )
          })
    
          <ul>
            {recipes}
          </ul>
          *3*</div>*3*
        );
      }
    }

    export default Recipes;

#### 6. Name three html input types. (NOTE: text is the default type - so it doesn't count in this case)
 
 //Your Answer
 Password, button, onsubmit?
 
 //Googled Answer
 
input type="password">
input type="button">
input type="submit">
input type="image">
 
 
 #### 7. How would you explain state to a friend who doesn't know code?
 
 //Your Answer
 State is the default setting for a few things we're keeping track of; we can update the default with a few actions as needed so those settings will be ready for other things.
 
 
 //Googled Answer
 State can simply be understood as a value at that point in time of the particular component/app.
 Components data will be stored in component's State. This state can be modified based on user action or other action. 
 
 #### 8. What is the difference between component state and props? Your answer should include a short explanation of both.
 
 
 //Your Answer
 Component state is the 'master' data, held most commonly in the main or 'App' component.  This can be anything; I had just background color and label color as my state when doing the ColorBox challenge.
 
 Props are when state is passed to other components by the main or 'App' component as this.state.example (if there was no destructuring).  Within the 'child' component that is being passed the prop, we'd call on that by saying this.props.example, which would allow the component/method to grab that value of the state and use it as needed - without impacting state unless we wanted to send it back and update state.
 
 //Googled Answer
 Props and state are related. The state of one component will often become the props of a child component. Props are passed to the child within the render method of the parent as the second argument to React.createElement() or, if you're using JSX, the more familiar tag attributes.

 <MyChild name={this.state.childsName} />
 The parent's state value of childsName becomes the child's this.props.name. From the child's perspective, the name prop is immutable. If it needs to be changed, the parent should just change its internal state:

 this.setState({ childsName: 'New name' });
 and React will propagate it to the child for you. A natural follow-on question is: what if the child needs to change its name prop? This is usually done through child events and parent callbacks. The child might expose an event called, for example, onNameChanged. The parent would then subscribe to the event by passing a callback handler.

 <MyChild name={this.state.childsName} onNameChanged={this.handleName} />
 The child would pass its requested new name as an argument to the event callback by calling, e.g., this.props.onNameChanged('New name'), and the parent would use the name in the event handler to update its state.

 handleName: function(newName) {
   this.setState({ childsName: newName });
 }
   
#### 9. Write a paragraph or so about your experience with building tic-tac-toe. Some topics to start with might be: things you learned about yourself, concepts from React that stood out to you, something about pair programming (if you paired), or the experience of building something in code from scratch.

Evan and I used TicTacToe as a way to wrap our heads around React; we used a lot of online examples, printed each part of the board out since it was just a 3x3, etc.
Seeing it all come together, even in a smaller scope where we felt like we were forcing state vs props and methods in more than one component, allowed us to really jump into Battleship
on better terms - not printing each of the 100 squares is one example.  Playing with destructuring was really helpful here, as well - familiarity around the syntax here helped us just move that much quicker through setting up Battleship.
I think something I learned about myself with pairing is if I have a partner who is on my level, I can go further than on my own and understand more than with a partner who had a hard time following the lecture.
I'm also pretty good at the big picture logic, and bringing the immediate action back to what we are working toward, but maybe need to drive more because the syntax is not my strong point recently.  
I think it's hard to force that issue because it's asking for a lot more patience from my partner in those moments to have to be walked through more explicitly what to type out when I'm drawing a blank.