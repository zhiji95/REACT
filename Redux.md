# Redux
## 1. Store
- Central Store: store entire application state
- Component: wants to manipulate app state
- Actions: despatch from component(js code), information package sent out
- Reducer: 
    1. check the action
    2. change the store
    3. sync code only
- Subscriptions: central store triggers subscription and subscription passes updated state as props
```javascript
const redux = require('redux')
const createStore = redux.createStore

const initialState = {
    counter: 0
}
// Reducer
const rootReducer = (state = initialState, action) => {
    if (action.type == 'INC_COUNTER') {
        // You can not do state.counter++, this is immutable
        return {
            ...state,
            counter: state.counter + 1
        }
    }
    if (action.type == 'ADD_COUNTER') {
        // You can not do state.counter++, this is immutable
        return {
            ...state,
            counter: state.counter + action.payload.value
        }
    }
    return state;
};

// Store
const store = createStore(rootReducer)

// Dispatching Action
store.dispatch({type: 'INC_COUNTER'});
store.dispatch({type: 'ADD_COUNTER', payload: {value: 10}});

// Subscription
store.subscribe(() => {
    console.log('[Subscription]', store.getState());
}

)
```

## 2. Middleware
- we can add middleware between action and reducer
```javascript
import {createStore, combineReducers, applyMiddleware} from 'redux'

const rootReducer = combineReducers({
    ctr: counterReducer,
    res: resultReducer
})

const store = createStore(rootReducer, applyMiddleware(logger));

const logger = store => {
    return next => {
        return action => {
            const result = next(action);
            return result
        }
    }
}
```
