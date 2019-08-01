# Core React Concepts

## 1. Setup local react project
#### 1. Using a Build Workflow:
- Dependency Management tools: npm, yarn
- Bundler: Webpack
- Compiler: Babel + Presets
- Development Server

#### 2. Create React App: 
[Install node.js](https://nodejs.org/en/)
[Create React project](https://github.com/facebook/create-react-app)
```
sudo npm install create-react-app -g
sudo create-react-app my-app
npm start
```

## 2. Folder Structure
- `package.json`: Dependencies, Scripts
- `node_modules`: hold all dependencies (generated automatically)
- `public`:
index.html (where react application mounts)
manifest.json: metadata
- `src`: react application
index.js: 
App.js: react component
App.test.js: unit test

## 3. Component

## 4. JSX
```javascript
// JSX
function App() {
    render() {
        return (
            <div className="App">
            <h1>Hi, I'm a React App</h1>
            </div>
        )
    }
}
// Above code got compiled into this code
function App() {
  return React.createElement('div'/*element*/, {className: 'App'}/*optional js object for configuration*/, React.createElement('h1'/*children*/, null, 'Hi, I\'m a React App!!!'/*children*/))
}
```

## 5. Create component
- Import React
- Export default
- import it in App.js without .js
- Set props (props.children)
- State (managed inside component)
- `this` refers class
- `onClick` not `onclick`
- Don't pass parentheses for handler
- Don't alter state like: `this.state.persons[0].name = "Maximalian";`
But use setState()

## 6. useState Hook
```javascript
const stateArr = useState({
    persons: [
      { name: 'Max', age: 28},
      { name: 'Manu', age: 29},
      { name: 'Stephanie', age: 26}
    ]
  }
stateArr[0] // State
stateArr[1] // A function allows to update
```

## 7. Stateful, Stateless
- Stateful: 
- Stateless: no internal state management

## 8. Passing Method between components:
`click={this.switchNameHandler.bind(this, 'Max!')`

## 9. Styling
- Css code is global
- We can define a style in Js file like:
```javascript
const style = {
      backgroundColor: 'white',
      font: 'inherit',
      border: '1px solid blue',
      padding: '8px',
      cursor: 'pointer'
    };
    
<button 
    style={style}
    onClick={ () => this.switchNameHandler('Maximalian!!') }>Switch Name</button>
```
