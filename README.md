
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