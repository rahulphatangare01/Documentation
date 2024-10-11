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
11.  <b> How do you handle optimistic updates in Redux Toolkit? </b>
</summary>

Optimistic updates allow your UI to reflect changes immediately, even before the server confirms the action. If the server
request fails, you can roll back the changes.

**Steps for Optimistic Updates:**

- Dispatch the optimistic update: Update the Redux store immediately, assuming the request will succeed.
- Make the API call: Perform the asynchronous request.
- Handle success: Do nothing or fine-tune the state based on the response.
- Handle failure: Revert the state to its previous value if the request fails.

```jsx harmony
const updateItem = createAsyncThunk(
  "item/updateItem",
  async (item, { rejectWithValue }) => {
    try {
      const response = await fetch(`https://api.example.com/items/${item.id}`, {
        method: "PUT",
        body: JSON.stringify(item),
      });
      return await response.json();
    } catch (error) {
      return rejectWithValue(error.message);
    }
  }
);

const itemSlice = createSlice({
  name: "item",
  initialState: { items: [], error: null },
  reducers: {
    // Optimistically update the item in the state
    updateItemOptimistically: (state, action) => {
      const index = state.items.findIndex((i) => i.id === action.payload.id);
      if (index !== -1) {
        state.items[index] = action.payload;
      }
    },
  },
  extraReducers: (builder) => {
    builder
      .addCase(updateItem.fulfilled, (state, action) => {
        // Update success - nothing extra to do
      })
      .addCase(updateItem.rejected, (state, action) => {
        // Revert optimistic update if API call failed
        state.error = action.payload;
      });
  },
});

export const { updateItemOptimistically } = itemSlice.actions;
```

</details>

<details>
<summary>
12.  <b>  How would you handle multiple slices sharing the same action in Redux Toolkit? </b>
</summary>
In Redux Toolkit, you can handle the same action across multiple slices by defining a common action and handling it in the extraReducers of multiple slices.

```jsx harmony
// Shared action
export const resetState = createAction("app/resetState");

// Slice 1
const slice1 = createSlice({
  name: "slice1",
  initialState: { data: [] },
  reducers: {},
  extraReducers: (builder) => {
    builder.addCase(resetState, (state) => {
      state.data = []; // Reset state for slice1
    });
  },
});

// Slice 2
const slice2 = createSlice({
  name: "slice2",
  initialState: { items: [] },
  reducers: {},
  extraReducers: (builder) => {
    builder.addCase(resetState, (state) => {
      state.items = []; // Reset state for slice2
    });
  },
});

export const { reducer: reducer1 } = slice1;
export const { reducer: reducer2 } = slice2;
```

Both slices handle the `resetState` action and reset their individual state.

</details>

<details>
<summary>
13.  <b>How would you structure a Redux store for a large-scale application with multiple modules? </b>
</summary>

For large-scale applications, it's important to modularize the Redux store into smaller, manageable slices that represent different features or domains. This allows for better scalability and maintainability.

**Steps:**

1. Feature-based slices: Each feature or domain has its own slice and reducer.
2. Root reducer: Combine individual reducers using combineReducers.
3. Modular structure: Organize slices and their corresponding logic (e.g., thunks, selectors) into separate files or folders.

```jsx harmony
// store.js
import { configureStore } from "@reduxjs/toolkit";
import userReducer from "./features/user/userSlice";
import postsReducer from "./features/posts/postsSlice";

const store = configureStore({
  reducer: {
    user: userReducer,
    posts: postsReducer,
  },
});

export default store;
```

```jsx harmony
src/
├── features/
│   ├── user/
│   │   ├── userSlice.js
│   └── posts/
│       ├── postsSlice.js
└── store.js

```

</details>

<details>
<summary>
14.  <b>How can you improve Redux performance with selective re-rendering? </b>
</summary>
Redux can cause unnecessary re-renders if components subscribe to the entire state instead of specific parts of the state. This can be mitigated by:

1. Using `useSelector` carefully: Only subscribe to the slice of state that the component needs.
2. Memoizing selectors: Use Reselect or `createSelector` to memoize selectors and prevent recomputation.
3. Splitting reducers: Split large state objects into smaller slices so that changes in one slice don’t trigger re-renders in unrelated parts of the state.

**Code Example (Using createSelector):**

```jsx harmony
import { createSelector } from "@reduxjs/toolkit";

const selectItems = (state) => state.items;
const selectActiveItems = createSelector(selectItems, (items) =>
  items.filter((item) => item.active)
);

const MyComponent = () => {
  const activeItems = useSelector(selectActiveItems); // Only re-renders when active items change
  return (
    <div>
      {activeItems.map((item) => (
        <div key={item.id}>{item.name}</div>
      ))}
    </div>
  );
};
```

</details>

<details>
<summary>
15.  <b>What is the role of configureStore in Redux Toolkit, and how is it different from the legacy createStore? </b>
</summary>

`configureStore` is a helper function in Redux Toolkit that wraps around `createStore` but with additional benefits:

- Automatically sets up good defaults like Redux DevTools and `redux-thunk` middleware.
- Allows easy integration of additional middleware without manual configuration.
- It simplifies store setup by removing the need for boilerplate code like `applyMiddleware`.

```jsx harmony
import { configureStore } from "@reduxjs/toolkit";
import userReducer from "./userSlice";

const store = configureStore({
  reducer: {
    user: userReducer,
  },
});

export default store;
```

**Differences**:

1. **Middleware**: configureStore includes middleware like Thunk by default, while createStore requires manual middleware setup.
2. **DevTools**: configureStore enables Redux DevTools automatically, while createStore requires explicit configuration.
3. **Immutability** checks: configureStore includes checks that ensure the state is not mutated accidentally.

</details>

<details>
<summary>
16.  <b> What are middleware in Redux, and how do you apply custom middleware in Redux Toolkit? </b>
</summary>

Middleware are functions that sit between the action dispatch and the reducer. They allow you to intercept actions, log them, modify them, or even delay their execution (as with Thunk).

Applying custom middleware in Redux Toolkit: You can add custom middleware using the middleware option in configureStore.

```jsx harmony
const loggerMiddleware = (store) => (next) => (action) => {
  console.log("Dispatching:", action);
  const result = next(action);
  console.log("Next state:", store.getState());
  return result;
};

const store = configureStore({
  reducer: {
    user: userReducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware().concat(loggerMiddleware), // Custom middleware
});
```

</details>

<details>
<summary>
17.  <b>How do you handle pagination in Redux with createAsyncThunk? </b>
</summary>

Pagination can be handled by passing parameters (like page and limit) to your thunk action and maintaining the pagination state in your slice.

```jsx harmony
export const fetchPaginatedData = createAsyncThunk(
  "data/fetchPaginatedData",
  async ({ page, limit }) => {
    const response = await fetch(
      `https://api.example.com/data?page=${page}&limit=${limit}`
    );
    return await response.json();
  }
);

const dataSlice = createSlice({
  name: "data",
  initialState: { items: [], page: 1, totalPages: 0 },
  reducers: {},
  extraReducers: (builder) => {
    builder.addCase(fetchPaginatedData.fulfilled, (state, action) => {
      state.items = action.payload.items;
      state.page = action.payload.page;
      state.totalPages = action.payload.totalPages;
    });
  },
});

export default dataSlice.reducer;
```

</details>
