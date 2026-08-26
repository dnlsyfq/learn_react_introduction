
```
const navBar = <p> </p>;
const navBar = <nav> </nav>;

const myTeam = {
  center: <li>Benzo Walli</li>,
  powerForward: <li>Rasha Loa</li>,
  smallForward: <li>Tayshaun Dasmoto</li>,
  shootingGuard: <li>Colmar Cumberbatch</li>,
  pointGuard: <li>Femi Billon</li>
};

```

* Attributes in JSX
```
<a href='http://www.example.com'>Welcome to the Web</a>;

const title = <h1 id='title'>Introduction to React.js: Part I</h1>; 

const panda = <img src='images/panda.jpg' alt='panda' width='500px' height='500px'>;

```

* Nested JSX

```
<a href="https://www.example.com"><h1>Click me!</h1></a>



```

* Multiline JSX 
```
(
  <a href="https://www.example.com">
    <h1>
      Click me!
    </h1>
  </a>
)


 const theExample = (
   <a href="https://www.example.com">
     <h1>
       Click me!
     </h1>
   </a>
 );

```

* Outer Elements
JSX expression must have exactly one outermost element i.e. div

```
const paragraphs = (
  <div id="i-am-the-outermost-element">
    <p>I am a paragraph.</p>
    <p>I, too, am a paragraph.</p>
  </div>
);

```

doesnt work
```
const paragraphs = (
  <p>I am a paragraph.</p> 
  <p>I, too, am a paragraph.</p>
);
```

The first opening tag and the final closing tag of a JSX expression must belong to the same JSX element

* Rendering JSX

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
root.render(<h1>Hello</h1>);


```

* Passing variable to render 
```
const toDoList = (
  <ol>
    <li>Learn React</li>
    <li>Become a Developer</li>
  </ol>
);

const container = document.getElementById('app');
const root = createRoot(container);
root.render(toDoList);

```

* Virtual DOM
only updates DOM elements that have changed.
```
const hello = <h1>Hello world</h1>;

// This will add "Hello world" to the screen:
root.render(hello, document.getElementById('app'));

// This won't do anything at all:
root.render(hello, document.getElementById('app'));


```

```
var React = require('react');
var ReactDOM = require('react-dom');

var MyComponent = React.createClass({
  render() {
    return <h1></h1>;
  }
});

ReactDOM.render(<MyComponent />, document.getElementById('app'));

```

* Advanced JSX 

HTML VS JSX
```
<h1 class="big">Title</h1>


<h1 className="big">Title</h1>


```

* Self enclosing tags

```
// Fine in JSX:
<br />

```

* Curly Braces in JSX
```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
// Write code here:
root.render(<h1>{2 + 3}</h1>);
```

* method 1
```
import React from 'react';
import ReactDOM from 'react-dom';



const pi = (
  <div>
    <h1>
      PI, YALL!
    </h1>
    <p>
      {Math.PI.toFixed(20)}
    </p>
  </div>
);

ReactDOM.render(
	pi,
	document.getElementById('app')
);
```

* method 2

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
// Write code here:

var math = <h1>2 + 3 = {2 + 3}</h1>;

root.render(math);
```

* Variables in JS

```
// Declare a variable:
const name = 'Gerdo';

// Access your variable inside of a JSX expression:
const greeting = <p>Hello, {name}!</p>;

```

* Variable Attributes in JSX

```
// Use a variable to set the `height` and `width` attributes:

const sideLength = "200px";

const panda = (
  <img 
    src="images/panda.jpg" 
    alt="panda" 
    height={sideLength} 
    width={sideLength} />
);

```

```
const pics = {
  panda: "http://bit.ly/1Tqltv5",
  owl: "http://bit.ly/1XGtkM3",
  owlCat: "http://bit.ly/1Upbczi"
}; 

const panda = (
  <img 
    src={pics.panda} 
    alt="Lazy Panda" />
);

const owl = (
  <img 
    src={pics.owl} 
    alt="Unimpressed Owl" />
);

const owlCat = (
  <img 
    src={pics.owlCat} 
    alt="Ghastly Abomination" />
); 

```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
const goose = 'https://content.codecademy.com/courses/React/react_photo-goose.jpg';

// Declare new variable here:
const gooseImg = <img src={goose} />

root.render(gooseImg);

```

* JSX Event Listeners

```
function clickAlert() {
  alert('You clicked this image!');
}

<img onClick={clickAlert} />

```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
function makeDoggy(e) {
  // Call this extremely useful function on an <img>.
  // The <img> will become a picture of a doggy.
  e.target.setAttribute('src', 'https://content.codecademy.com/courses/React/react_photo-puppy.jpeg');
  e.target.setAttribute('alt', 'doggy');
}

const kitty = (
	<img 
    onClick={makeDoggy}
		src="https://content.codecademy.com/courses/React/react_photo-kitty.jpg" 
		alt="kitty" />
);

root.render(kitty);
```

* Conditional Statements

```
(
  <h1>
    {
      if (purchase.complete) {
        'Thank you for placing an order!'
      }
    }
  </h1>
)

```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
let message;

if (user.age >= drinkingAge) {
  message = (
    <h1>
      Hey, check out this alcoholic beverage!
    </h1>
  );
} else {
  message = (
    <h1>
      Hey, check out these earrings I got at Claire's!
    </h1>
  );
}

root.render(message);
```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
function coinToss() {
  // This function will randomly return either 'heads' or 'tails'.
  return Math.random() < 0.5 ? 'heads' : 'tails';
}

const pics = {
  kitty: 'https://content.codecademy.com/courses/React/react_photo-kitty.jpg',
  doggy: 'https://content.codecademy.com/courses/React/react_photo-puppy.jpeg'
};

let img;

// if/else statement begins here:
if(coinToss()==='heads'){
  img = <img src={pics.kitty} />
} else {
  img = <img src={pics.doggy} />
}

root.render(img);
```

* Terniary
```
const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);

```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
function coinToss () {
  // Randomly return either 'heads' or 'tails'.
  return Math.random() < 0.5 ? 'heads' : 'tails';
}

const pics = {
  kitty: 'https://content.codecademy.com/courses/React/react_photo-kitty.jpg',
  doggy: 'https://content.codecademy.com/courses/React/react_photo-puppy.jpeg'
};

const img = <img src={pics[x ? y : z]} />;

const img = <img src={ pics[coinToss() === 'heads' ? 'kitty':'doggy'] };

root.render(img);
```

* && conditionals
If the expression on the left of the && evaluates as true, then the 
JSX on the right of the && will be rendered. If the first expression is false, however, then the JSX to the right of the && will be ignored and not rendered.
```
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);

```

```
const strings = ['Home', 'Shop', 'About Me'];

const listItems = strings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>

```

* components

```
function MyComponent() {
  return <h1>Hello, I'm a functional React Component!</h1>;
}

export default MyComponent;

```


> App.js file is the top level of your application, we have to export it to index.js to render., and index.js is the entry point.

index.js
```
import React from 'react';
import ReactDOM from 'react-dom/client';
import MyComponent from './App';

```

app.js
```
import React from 'react';

function MyComponent() {
  return <h1>Hello, this is a function component body.</h1>;
}

export default MyComponent;
```
```
// This is fine in JSX, not in an explicit array:
<ul>
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ul>

// This is also fine!
const liArray = [
  <li>item 1</li>, 
  <li>item 2</li>, 
  <li>item 3</li>
];

<ul>{liArray}</ul>

```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleList = people.map((person,i) =>
  // expression goes here:
  <li>{person}</li>
);

// root.render goes here:
root.render(<ul>{peopleList}</ul>);
```

* keys
A key is a JSX attribute. The attribute’s name is key. The attribute’s value should be something unique, similar to an id attribute
keys don’t do anything visible! React uses them internally to keep track of lists. If you don’t use keys when you’re supposed to, React might accidentally scramble your list items into the wrong order.
```
<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>

```

```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleList = people.map((person,i) =>
  // expression goes here:
  <li key={'person_' + i}>{person}</li>
);

// root.render goes here:
root.render(<ul>{peopleList}</ul>);
```

* react methods - .createElement

```
// JSX
const h1 = <h1>Hello world</h1>;



// WO JSX
const h1 = React.createElement(
  "h1",
  null,
  "Hello world"
);


```

* Advanced JSX
```
import React from 'react';
import { createRoot } from 'react-dom/client';

const container = document.getElementById('app');
const root = createRoot(container);
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleList = people.map((person,i) =>
  // expression goes here:
  <li key={'person_' + i}>{person}</li>
);

// root.render goes here:
root.render(<ul>{peopleList}</ul>);
```

* Nested JSX 
```
const myClasses = (
  <a href="https://www.codecademy.com">
    <h1>
      Sign Up!
    </h1>
  </a>
);
```

* JSX root
```

import React from 'react';
import { createRoot } from 'react-dom/client';
 
const container = document.getElementById('app');
const root = createRoot(container);
root.render(<h1>Render me!</h1>);
```

* JSX Attributes
```
const example = <h1 id="example">JSX Attributes</h1>;

const introClass = "introduction";
const introParagraph = <p className={introClass}>Hello world</p>;
```

* JSX className
```
// When rendered, this JSX expression...
const heading = <h1 className="large-heading">Codecademy</h1>;

// ...will be rendered as this HTML
<h1 class="large-heading">Codecademy</h1>
```

* JSX Conditionals


In JSX, && is commonly used to render an element based on a boolean condition. && works best in conditionals that will sometimes do an action, but other times do nothing at all.

If the expression on the left of the && evaluates as true, then the JSX on the right of the && will be rendered. If the first expression is false, however, then the JSX to the right of the && will be ignored and not rendered.
```
// If baby is false and age is above 25,
// all list items will display.
// Otherwise, only items meeting their conditions will show.
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);
```

```
// Using ternary operator
const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);

// Using if/else outside of JSX 
let text;

if (age >= drinkingAge) { text = 'Buy Drink' }
else { text = 'Do Teen Stuff' }

const headline = <h1>{ text }</h1>

// Using && operator. Renders as empty div if length is 0
const unreadMessages = [ 'hello?', 'remember me!'];

const update = (
  <div>
    {unreadMessages.length > 0 &&
      <h1>
        You have {unreadMessages.length} unread messages.
      </h1>
    }
  </div>
);
```

* JS in JSX
```
<p>{ Math.random() }</p>

// Above JSX will be rendered something like this: 
<p>0.88</p>
```

* JSX Event Listeners
```
// Basic example
const handleClick = () => alert("Hello world!");

const button = <button onClick={handleClick}>Click here</button>;

// Example with event parameter
const handleMouseOver = (event) => event.target.style.color = 'purple';

const button2 = <div onMouseOver={handleMouseOver}>Drag here to change color</div>;
```


* JSX Methods
```
const strings = ['Home', 'Shop', 'About Me'];

const listItems = strings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>

```

* JSX Syntax
```
<br />
<img src="example_url" />
```


* React.createElement
```
// The following JSX...
const h1 = <h1 className="header">Hello world</h1>;

// ...will be compiled to the following:
const h1 = React.createElement(
  'h1',
  {
    className: 'header',
  },
  'Hello world'
);

```

* React Components

```
import { createRoot } from 'react-dom/client';

function MyComponent(){
    return <h1>Hello world</h1>;
}

createRoot(document.getElementById('app')).render(<MyComponent />);


```
