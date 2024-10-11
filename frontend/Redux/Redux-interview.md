# Redux Interview questions

<details>
<summary>
1.  <b>What is Redux? Why do we use it in React applications? </b>
</summary>

Redux is a predictable state management library used in JavaScript applications. It helps manage the global state of an application in a centralized store. The main purpose of Redux is to make the state predictable, trackable, and easy to debug, especially in large applications where components need to share state.

**Key Concepts:**

- **Store**: Centralized state of the application.
- **Actions**: Payloads of information that send data from your application to the Redux store.
- **Reducers**: Pure functions that take the current state and an action as input and return a new state.
- **Dispatch**: Function to send actions to the store.
</details>

<details>
<summary>
2.  <b> What are the three core principles of Redux?</b>
</summary>

1. **Single Source of Truth**: The state of the entire application is stored in a single object (the store).
2. **State is Read-only**: The only way to change the state is by dispatching an action.
3. **Changes are Made with Pure Functions**: Reducers are pure functions that return new states based on the dispatched action.
</details>

<details>
<summary>
3.  <b>  How does the combineReducers function work?</b>
</summary>

`combineReducers` is a helper function that combines multiple reducer functions into a single reducing function, creating a state object with multiple properties corresponding to each reducer.

```jsx harmony
import { combineReducers } from "redux";
import userReducer from "./userReducer";
import postReducer from "./postReducer";

const rootReducer = combineReducers({
  user: userReducer,
  posts: postReducer,
});

export default rootReducer;
```

</details>

<details>
<summary>
4.  <b> What is Redux Toolkit and why was it introduced?</b>
</summary>

Redux Toolkit (RTK) is a library that was introduced to simplify the configuration and setup of Redux. It provides a set of tools that simplify writing Redux logic by eliminating boilerplate code and making the code more maintainable. It includes prebuilt features like `createSlice`, `configureStore`, and `createAsyncThunk`.

**Key Features:**

1. Simplifies reducer and action creation with createSlice.
2. Automatically sets up the store with middleware like Redux Thunk.
3. Includes createAsyncThunk for handling asynchronous logic.
</details>

<details>
<summary>
5.  <b> What is Thunk middleware in Redux? Why is it used?</b>
</summary>

Thunk is a middleware that allows you to write action creators that return a function instead of an action. This function can perform asynchronous tasks like API calls, dispatching actions once the API call is resolved.

**Why is it used?** Thunk is used to delay the dispatch of an action or to dispatch only if certain conditions are met. It is primarily used for handling async logic in Redux.

```jsx harmony
const fetchData = () => {
  return async (dispatch) => {
    dispatch({ type: "FETCH_DATA_REQUEST" });
    try {
      const response = await fetch("https://api.example.com/data");
      const data = await response.json();
      dispatch({ type: "FETCH_DATA_SUCCESS", payload: data });
    } catch (error) {
      dispatch({ type: "FETCH_DATA_FAILURE", error });
    }
  };
};
```

</details>

<details>
<summary>
6.  <b>How does createAsyncThunk work in Redux Toolkit? </b>
</summary>

createAsyncThunk is a utility in Redux Toolkit that allows you to handle async logic in a more standardized way. It automatically dispatches lifecycle actions (pending, fulfilled, rejected) based on the promise's state (pending, resolved, or rejected).

```jsx harmony
import { createSlice, createAsyncThunk } from "@reduxjs/toolkit";

// Async thunk for fetching data
export const fetchData = createAsyncThunk("data/fetchData", async () => {
  const response = await fetch("https://api.example.com/data");
  const data = await response.json();
  return data; // This is returned as the payload of the fulfilled action
});

// Slice
const dataSlice = createSlice({
  name: "data",
  initialState: {
    items: [],
    status: "idle", // 'idle' | 'loading' | 'succeeded' | 'failed'
    error: null,
  },
  reducers: {},
  extraReducers: (builder) => {
    builder
      .addCase(fetchData.pending, (state) => {
        state.status = "loading";
      })
      .addCase(fetchData.fulfilled, (state, action) => {
        state.status = "succeeded";
        state.items = action.payload;
      })
      .addCase(fetchData.rejected, (state, action) => {
        state.status = "failed";
        state.error = action.error.message;
      });
  },
});

export default dataSlice.reducer;
```

- **pending**: Dispatched when the async function starts.
- **fulfilled**: Dispatched when the async function succeeds, with the result as the payload.
- **rejected**: Dispatched when the async function fails, with the error as the payload.
</details>

<details>
<summary>
7.  <b>What is the difference between createAsyncThunk and manual Thunk actions in Redux? </b>
</summary>

`createAsyncThunk:`

- Provides a more standardized and structured way to handle async logic.
- Automatically dispatches pending, fulfilled, and rejected actions.
- Reduces boilerplate code.

**Manual Thunk:**

- More flexible but requires writing the entire async action logic manually.
- You need to handle action dispatching (for loading, success, error) manually.
- Can be more verbose and error-prone compared to createAsyncThunk.

```jsx harmony
const fetchData = () => async (dispatch) => {
  dispatch({ type: "FETCH_DATA_PENDING" });
  try {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    dispatch({ type: "FETCH_DATA_SUCCESS", payload: data });
  } catch (error) {
    dispatch({ type: "FETCH_DATA_FAILURE", error: error.message });
  }
};
```

</details>

<details>
<summary>
8.  <b>What are the benefits of using createSlice in Redux Toolkit? </b>
</summary>

`createSlice` simplifies the process of creating reducers and action creators by automatically generating action types and action creators based on the reducers defined in the slice.

**Benefits**:

1. Reduces boilerplate code.
2. Automatically generates actions based on reducer names.
3. Cleaner and more maintainable code.
4. Integrates well with createAsyncThunk for handling async actions.

```jsx harmony
import { createSlice } from "@reduxjs/toolkit";

const counterSlice = createSlice({
  name: "counter",
  initialState: { value: 0 },
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    reset: (state) => {
      state.value = 0;
    },
  },
});

export const { increment, decrement, reset } = counterSlice.actions;
export default counterSlice.reducer;
```

</details>

<details>
<summary>
9.  <b> How would you handle multiple API calls in parallel using createAsyncThunk?</b>
</summary>

You can use `Promise.all` within the `createAsyncThunk` function to handle multiple API calls in parallel. This allows you to wait for all the promises to resolve before returning the final result.

```jsx harmony
export const fetchMultipleData = createAsyncThunk(
  "data/fetchMultipleData",
  async () => {
    const [response1, response2] = await Promise.all([
      fetch("https://api.example.com/data1"),
      fetch("https://api.example.com/data2"),
    ]);
    const data1 = await response1.json();
    const data2 = await response2.json();
    return { data1, data2 };
  }
);
```

</details>

<details>
<summary>
10.  <b>How do you cancel an ongoing createAsyncThunk request? </b>
</summary>

Redux Toolkit's createAsyncThunk supports cancellation of requests by utilizing an AbortController. You can pass an abortSignal to an async function and handle cancellation logic inside your thunk.

```jsx harmony
export const fetchDataWithCancel = createAsyncThunk(
  "data/fetchDataWithCancel",
  async (_, { signal }) => {
    const controller = new AbortController();
    signal.addEventListener("abort", () => {
      controller.abort();
    });
    const response = await fetch("https://api.example.com/data", {
      signal: controller.signal,
    });
    return await response.json();
  }
);
```

</details>

<details>
<summary>
11.  <b> </b>
</summary>
</details>

<details>
<summary>
12.  <b> </b>
</summary>
</details>

<details>
<summary>
13.  <b> </b>
</summary>
</details>

<details>
<summary>
14.  <b> </b>
</summary>
</details>

<details>
<summary>
15.  <b> </b>
</summary>
</details>

<details>
<summary>
16.  <b> </b>
</summary>
</details>
