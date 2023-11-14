##### As a React developer, we are very much acquainted with `useEffect` led data fetching. In doing we use multiple `useState` (3 in following exmaple).

```
import { useState, useEffect } from "react";
import axios from "axios";

export const DataFetchingOne = () => {
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState("");
  const [post, setPost] = useState({});

  useEffect(() => {
    axios
      .get("https://jsonplaceholder.typicode.com/posts/1")
      .then((response) => {
        setLoading(false);
        setError("");
        setPost(response.data);
      })
      .catch((err) => {
        console.log("errorMsg", err);
        setLoading(false);
        setError("Some thing went wrong");
        setPost({});
      });
  }, []);

  return (
    <div>
      {loading ? "Loading..." : post.title}
      {error ?? null}
    </div>
  );
};
```
##### But using `useReducer` hook, we can gracefully handle this data fetching where there is requirement of multiple `state`. 

```
import { useReducer, useEffect } from "react";
import axios from "axios";

const initialState = {
  loading: true,
  error: "",
  post: {}
};

const reducer = (state, action) => {
  switch (action.type) {
    case "FETCH_SUCCESS":
      return {
        loading: false,
        error: "",
        post: action.payload
      };
    case "FETCH_ERROR":
      return {
        loading: false,
        error: "Something went wrong",
        post: {}
      };
    default:
      return state;
  }
};

export const DataFetchingTwo = () => {
  const [state, dispatch] = useReducer(reducer, initialState);

  useEffect(() => {
    axios
      .get("https://jsonplaceholder.typicode.com/posts/1")
      .then((response) => {
        dispatch({ type: "FETCH_SUCCESS", payload: response.data });
      })
      .catch((err) => {
        dispatch({ type: "FETCH_ERROR" });
      });
  }, []);

  return (
    <div>
      {state.loading ? "Loading..." : state.post.title}
      {state.error ?? null}
    </div>
  );
};
```

###### This [link](https://codesandbox.io/s/data-fetching-usestate-vs-usereducer-2ld7wx) is the demontration of above usecase. 
 
