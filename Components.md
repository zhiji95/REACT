# Components
## 1. Project Structure
- index.js in source directory
- A list of containers
- A list of components

## 2. Components
- Stateful components: we have set and call this.setState() to manage state.
- Stateless components (the majority): 
```javascript
const componentName = (props) => {

}
```
- Class-based components: supports access to state and lifecycle hook 
```javascript
class componentName extends Component {
    this.state.stateName
    this.props.propsName
}
```
- Functional components: not supports lifecycle hooks
```javascript
const componentName = props => {
    props.propsName
}
```
## 3. Component lifecycle
#### create
- `constructor(props)`: set up state, call super(props)
- `getDerovedStateFromProps(props, state)`: sync state
- `render()`: prepare and structure your JSX code
- render child components
- `componentDidMount()`: Cause side-effect, don't call setState here!
#### update
- `getDerivedStateFromProps(props, state)`: Sync state to props.
- `shouldComponentupdate(nextProps, nextState)`: decide whether to countinue or not.
- `render()`: prepare and structure your JSX code
- render child components
- `getSnapShotBeforeUpdate(prevProps, prevState)`: Last minute DOM ops
- `componentDidupdate(prevProps, preState, snapShot)`: Cause side-effect

## 4. useEffect()
- `useEffect()`: a react hook combines functionalities of all lifecycle hook
```javascript
import React, {useEffect} from 'react'

useEffect(() => {
    console.log("useEffect"); 

    setTimeout(() => {
        alert('sssss');
    }, 1000);
}, [props.persons]); //we only runs when props.persons changed
```
