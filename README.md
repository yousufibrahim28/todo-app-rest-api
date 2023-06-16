# todo-app-rest-api
Rest API to connect to the front end todo app

React Single Page application and react basics

JWT = Jason Web Tokens

Full Stack architecture typically follows

- Frontend - React Application - will run on web browser
- Restful API - Spring Boot or Java - will run on server
- Database - will run on server

- Full Stack Architecture 
- Front-end: React Framework 
    - Modern JavaScript 
- Backend REST API: Spring Boot 
- Database 
    - H2 > MySQL 
- Authentication 
    - Spring Security (Basic > JWT) 


- Why Full-Stack Architecture?
- Full Stack Architectures are complex to build 
    - You need to understand different language
    - You need to understand a variety of frameworks 
    - You need to use a variety of tools 
- Why Full-Stack?
    - Because they give you flexibility and allow reuse of REST API 
        - OPTION: Create a Mobile App talking to REST API 
        - OPTION: Create an IOT App talking to REST API 


- Quick Look into JavaScript History
    - JavaScript evolved considerably in the last decade or so 
        - (EARLIER JS Versions) Very difficult to write maintainable JavaScript code
        - Improved drastically in the last decade 
            - JAVASCRIPT VERSIONS 
                - ES5 - 2009 
                - ES6 - 2015 - ES2015 
                - ES7 - 2016 - ES2016 ...
                - ES13 - 2022 - ES2022 
                - ES14 - 2023 - ES2023 ... 
- ES: ECMASCRIPT 
        - EcmaScript is standard 
        - JavaScript is implementation 


Npm - Node package manager
- It is similar to maven or Gradle for Java/ Spring-boot
- This helps to manage Javascript library and run Javascript on machine without the need for a browser.
- We can download dependency - Use `npm install <pkg>` - and install
- save it as a dependency in the package.json file. To use in our project.

npm init - command will create a new project/package.json file and will ask bunch of questions for setting up

npm init -y - command will create projects with defauls for all the question


  "dependencies": {
    "jquery": "^3.7.0" - ^ this indicates automatically update to any 3.X.X versions but not update to 4.x.x
  }


- React is the popular framework for creating SPA- Single page Application. Instead of refreshing the whole page when updated it just updates the particular part of the page
    - Popular alternatives: Angular, VueJS 
- Open-source project created by Facebook 
- Component-Based 
- Mostly used to build front-end web SPA applications Can also be used to create native apps for Android, iOS (React Native) 

Creating React App with Create React App 
- Create React App: Recommended way to create a new single- page application (SPA) using React 
- Compatible with macOS, Windows, and Linux 
- Prerequisite: Latest version of Node JS
    - NPM - package manager: Install, delete, and update JS packages (npm --version) 
    - NPX - package executer: Execute JS packages directly, without installing 
    - Let's get started: 
- DO NOT WORRY:Troubleshooting instructions at the end of the video! cd YOUR_FOLDER
    - npx create-react-app todo-app
    - cd todo-app 
    - npm start 



- Troubleshooting
- Windows: Launch command prompt as administrator 
- Mac or Linux: Use sudo
    - sudo npx create-react-app todo-app  
- Other things you can try:
    - npm uninstall -g create-react-app
    - npx clear-npx-cache
- Complete troubleshooting guide: 
    - Google for "create react app troubleshooting" 


- Important Commands
- npm start: Runs the app in development mode 
    - Recommendation: Use Google Chrome 
- npm test: Run unit tests 
- npm run build: Build a production deployable unit 
    - Minified 
    - Optimized for performance 
- npm install --save react-router-dom: Add a dependency to your project 



- Goal: Get a 10,000 feet overview of folder structure 
    - README.md: Documentation 
    - package.json: Define dependencies (similar to Maven pom.xml) 
    - node_modules: Folder where all the dependencies are downloaded to 
    - React Initialization 
        - public/index.html: Contains root div
        - src/index.js: Initializes React App. Loads App component. 
            - src/index.css - Styling for entire application 
        - src/App.js: Code for App component 
            - src/App.css - Styling for App component 
            - src/App.test.js - Unit tests for App component 
                - Unit test is right along side production code (Different to Java approach) 

- Why do we need React Components? 
- Web applications have complex structure
    - Menu, Header, Footer, Welcome Page, Login Page, Logout Page, Todo Page etc 
- Components help you modularize React apps 
    - Create separate components for each page element 
        - Menu Component 
        - Header Component 
        - Footer Component .. 
- Why? 
    - Modularization 
    - Reuse 

- Understanding React Components 
- First component typically loaded in React Apps: App Component 
- Parts of a Component 
    - View (JSX or JavaScript) 
    - Logic (JavaScript)
    - Styling (CSS)
    - State (Internal Data Store) Props (Pass Data) 
- (Remember) React component names must always start with a capital letter 



function FirstComponent() { // these are called function components in react.
  return (
    <div class="FirstComponent"> Fist Component</div>
  )
}

There is another type of component called class component.

import { Component } from 'react'; - Import this on top


class ThirdComponent extends Component {
  render() {
    return (
      <div class="ThirdComponent"> Third Component</div> // This we are returning is JSX
    )
  }
}


Ideally each component should be in it own file.



When to use function component and Class Component?

- State : Built-in React Object used to contain data or information about the component
- In earlier version of react, Only Class components can have state
    - And implementing state was very complex
- Hooks were introduced in React 16.8
    - Hooks are very easy to use
    - useState hook allows adding state to function Components
- If we are using React 16.8 or above, it is always recommended to go with function components.

Why are we using parenthesis () in return of every component? Because of JSX

- Paranthesis makes returning complex JSX code easier
	
- Getting Started with JSX - Views with React 
- React projects use JSX for presentation 
- Stricter than HTML 
    - Close tags are mandatory 
    - Only one top-level tag allowed: 
        - Cannot return multiple top-level JSX tags 
        - Wrap into a shared parent
            - <div>...</div> or <>...</> (empty wrapper) 
- How is JSX enabled in a React project? 
    - Different browsers have different support levels modern JS features (ES2015,..,ES2022,..)
        - How to ensure backward compatibility for your JS code? 
        - Solution: Babel
        - Babel also converts JSX to JS 
        - Babel is a JavaScript Compiler
        - https://babeljs.io/

- Let's Play with Babel and JSX 
    - Let's try Babel: https://babeljs.io/repl 
        - How does JSX get converted to JS? 
            - Example 1: <h1 className="something" attr="10">heading</h1>
            - Example 2: <Parent attr="1"><Child><AnotherChild></AnotherChild></Child> </Parent> 
    - Following are examples of ERRORs 
    - <h1></h1><h2></h2>
        - SOLUTION: wrap with <div>...</div> or <>...</> (empty wrapper) 
    - Close tags are mandatory 
- Let's try JSX in our component
    - Parentheses () make returning complex JSX values easier 
    - Custom Components should start with upper case letter 
        - For HTML you should use small case 
    - Specify CSS class - className 
        - Similar to HTML class attribute 


JavaScript Best Practises or React best practises.

- 1: Each component in its own file (or module) 
    - src\components\learning-examples\FirstComponent.jsx 
    - Exercise: Move SecondComponent, ThirdComponent & FourthComponent to their own modules 
    - To use a class from a different module, you need to import it 
    - Default import 
        - import FirstComponent from './components/learning/FirstComponent.jsx'; 
    - Named import 
        - import { FifthComponent } from './components/learning/FirstComponent.jsx'; 
- 2: Exercise: Create LearningComponent and move all code in App component to it! 

import {FifthComponent} from './components/learning-examples/FirstComponet'; // If we want to import something that is not deflaut component but eligible for importing (in the same file) we have to use this {}



- Options of styling your React components 
- 1: style
    - Error: <button style={border-radius:30px}> 
    - Correct Syntax: <button style={{borderRadius:"30px"}> 
- 2: className
    - Define the cssClass in your component CSS file 


- Understanding State in React
- State: Built-in React object used to contain data or information about the component 
- (REMEMBER) In earlier versions of React, ONLY Class Components can have state 
    - AND implementing state was very complex! 
- Hooks were introduced in React 16.8 
    - Hooks are very easy to use
    - useState hook allows adding state to Function Components 
        - useState returns two things 
            - 1: Current state 
            - 2: A function to update state
- Each instance of component has it's own state 
- How to share state between components? 
    - Move state “upwards” (to a parent component) 



- What's happening in the background with React?
    -  We updated the state => React updated the view 
    - How can you update an HTML element? 
        - A HTML page is represented by DOM (Document Object Model)
        - Each element in a HTML page is a node in the DOM
        - You need to update the DOM to update the element
        - HOWEVER, writing code to update the DOM can be complex and slow! 
- React takes a different approach:
    - Virtual DOM: “virtual” representation of a UI (kept in memory) 
        - React code updates Virtual DOM
    - React identifies changes and synchronizes them to HTML page 
    - 1: React creates Virtual DOM v1 on load of page 
    - 2: You perform an action 
        - 3: React creates Virtual DOM v2 as a result of your action 
        - 4: React performs a diff between v1 and v2
        - 5: React synchronizes changes (updates HTML page) 
- Summary: We are NOT updating the DOM directly! 
    - React identifies changes and efficiently updates the DOM 

You can pass “props” (short for properties) object to a React Component 
Used for things that remain a constant during lifetime of a component Example increment value of a specific component 



React Form has a state and Dom value.

Controlled component. And Uncontrolled component.


React router

npm install react-router-dom - run this command to add this to your dependency.
 Stop server add the above dependency start the server

When creating Single Page Applications - the entire page should not be refreshed, instead only the component should be refreshed.

Use Auth Context to share authentication state with multiple components

// Create a Context

// Put Some Some state in the context

// Share the created context with other components



// Use Axios framework to call REST API.
// Use Formik framework for Form management
// Use moment framework for Date handling


Remember to Validate all Form fields

While Authenticating - there is a preflight call who goes to server to check whether the auth token is valid, This basically sends a Http.Options method and verifies, so we might need to allow Http.Options method alone to verify the auth token


Getting Started with JWT 
- Basic Authentication 
    - No Expiration Time 
    - No User Details 
    - Easily Decoded 
- How about a custom token system? 
    - Custom Structure 
    - Possible Security Flaws 
    - Service Provider & Service Consumer should understand 
- JWT (Json Web Token) 
    - Open, industry standard for representing claims securely between two parties 
    - Can Contain User Details and Authorizations 

What does a JWT contain? 

- Header 
    - Type: JWT
    - Hashing Algorithm: HS512 
- Payload
    - Standard Attributes 
    - iss: The issuer
    - sub: The subject
    - aud: The audience
    - exp: When does token expire? 
    - iat: When was token issued? 
    - Custom Attributes
        - youratt1: Your custom attribute 1 
- Signature 
    - Includes a Secret 

- Send POST to http://localhost:8080/authenticate 
    - Get the TOKEN_VALUE from response 
- Use token in authorization header for future API calls: 
    - Authorization : "Bearer TOKEN_VALUE"


Jwt.io // to verify if the token generated is a valid token
  
  
  
 ** Unit testing with JUnit and Mockito**

Large applications can have 1000s of code files ad millions of lines of code

Testing: Check app behaviour against expected behaviour
    - Option 1: Deploy the complete application and test
        - This is called System Testing or Integration Testing
    - Option 2: Test specific units of application code independently
        - Examples: A specific method or group of methods
        - This is called Unit Testing
        - Advantages of Unit Testing
            - Find bugs early(run under CI)
            - Easy to fix bugs
            - Reduces Costs in the long run
        - Most Popular Java Frameworks: Unit and Mockito
- Recommended: Option 1 + Option 2


AfterAll and BeforeAll annotations should be static

Junit Examples : https://github.com/in28minutes/master-spring-and-spring-boot/tree/main/51-junit


Mockito

- Great unit test => Easier Maintenance
- However, writing great units is nOT easy
    - Applications Have multiple layers
        - Each class has dependencies
- How do you write unit test for classes with multiple dependencies
    - Option 1: Stubs // the code grows, and there is a lot of maintenance head aches
    - Option2: Mocks  // this has better maintenance and easy to mock a dependency. No need to create stubs and new method implementations in the actual interface will not break our tests
        - Simpler to write
        - Easier to maintain
        - @ExtendWith(MockitoExtension.class), @Mock and @InjectMocks makes it more easier
        - We can return multiple values for a method in using Mockito mocks, last value will be the default value when called multiple times after the no.of returns is exhausted
        - Mockito.any is way to mock parameterised methods

Explore JMock and PowerMockito

Mockito Examples : https://github.com/in28minutes/master-spring-and-spring-boot/tree/main/52-mockito
