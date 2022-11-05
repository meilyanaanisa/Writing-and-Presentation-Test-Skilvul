# Rangkuman Materi Minggu Ke-7 Skilvul

## React Router

- Routing library yang paling sering digunakan di dalam react.
- Dengan router dapat membuat halaman menjadi lebih dynamic.
- Perpindahan halaman di router menggunakan path url
- Bagaimana instalasi router

    - install react melalui terminal
    
     original :
    > npx create-react-app my-app

    vite :
    > npm create vite@latest my-app 

    - install react-router melalui terminal
    > npm install react-router-dom

    - configurasi teh router, ketik di dalam index.js
    > import { BrowserRouter, Route, and Switch from react-router-dom }

    - menambahkan komponen BrowserRouter sebagai pembungkus App
    ```
    < BrowserRouter >
        <App />
      </ BrowserRouter >
    ```
- BrowserRouter sebuah alamat lokasi url pada browser agar react dapat berjalan
- Buat komponen halaman yang ingin ditampilkan seperti, about, recommend, blog dll.
```
const AboutStudent = () => {
  return (
    <>
      <h1>About Student</h1>
    </>
  );
};

export default AboutStudent;
```

- code pada App.jsx
```
import { Route, Routes, Link } from "react-router-dom"
import { Home } from "./Home"
import { BookList } from "./BookList"

export function App() {
  return (
    <>
      <nav>
        <ul>
       { /* Handling Navigation */ }
          <li><Link to="/">Home</Link></li>
          <li><Link to="/Books">Books</Link></li>
        </ul>
      </nav>

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/books" element={<BookList />} />
      </Routes>
    </>
  )
}
```

- Nested Router, perpindahan halaman berdasarkan parent halaman untuk child halaman.

```
<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/books">
    <Route index element={<BookList />} />
    {*/ Dynamix Routes */ }
    <Route path=":id" element={<Book />} />
    <Route path="new" element={<NewBook />} />
  </Route>
  <Route path="*" element={<NotFound />} />
</Routes>
```
- Outlet, memberikan render langsung kepada child component saat parent component dibuka
```
import { Outlet, Link } from "react-router-dom";

const aboutPage = () => {
  return (
    <>
      <Outlet />
      <Link to={"liststudent"}>About Student |</Link>
      <Link to={"listteacher"}>About Teacher</Link>
    </>
  );
};

export default aboutPage;

```
- Router lainnya selain BrowserRouter

    - Native Router
    - Hash Router, memiliki ciri khas # pada url
    - History Router
    - Memory Router
    - Static Router


## React-Redux

- Sebuah library dari javaScript 
- Sebagai state management, memudahkan aplikasi kita untuk di manage dikemas dalam sebuah store
- Menjalankan react-redux
> npm install react-redux

- Import provider ke dalam main.jsx. component yang memberikan akses ke store.
> import { Provider } from 'react-redux'

- Kenapa kita harus menggunakan react-redux

  - store, sebagai gudang aplikasi state 
  - manage aplikasi state
  - mendapat pemberitahuan apabila aplikasi state berubah

- Bagian dari redux

  **store**, sebuah gudang untuk menyimpan data object, tempat menampung state

  ```
  import { createStore } from 'redux';
  import todoReducer from './reducers';


  const store = createStore(todoReducer);
  ```

  **action**, JavaScript object yang memberikan informasi ke store. mengembalikan sebuah function dalam bentuk object.
  ```
  export function addTodo({ task }) {
  return {
    type: 'ADD_TODO',
    payload: {
      task,
      completed: false
    },
  }
  }

  // example returned value:
  // {
  //   type: 'ADD_TODO',
  //   todo: { task: '🛒 get some milk', completed: false },
  // }
  ```
  **reducer**, diibaratkan sebagai rak di dalam gudang, mengelola state yang ada di store. Parameter wajib dari reducer yaitu : state dan action.
  ```
  function myReducer(previousState, action) => {
  // use the action type and payload to create a new state based on
  // the previous state.
  return newState;
  }
  ```

## React-Redux-Thunk

- Sebuah middleware yang memungkinkan kita menulis function yang dapat berinteraksi dengan redux store.

- install package redux-thunk
> npm install redux-thunk

- update Redux store agar dapat menggunakan middleware
> import thunk from 'redux-thunk'

- import applyMiddleware
> import { createStore, applyMiddleware } from 'redux';

<!-- - Action creators
```
conts store = createStore(combineReducers) {
  return {
    todos: todosReducers,
    counter: counterReducers
  };
  applyMiddleware(logger, thunk)
}
``` -->

- memulai menggunakan redux-thunk
```
store.dispatch(dispatch => {
  dispatch({ type: "FETCH_LOADING"});

  fetch("link json")
  .then (res => res.json())
  .then (data => dispatch({ type : "FETCH_SUCCESS", payload:data }))
  .catch (error => dispatch({ type : "FETCH_ERROR",payload:error }));

})
```

- membuat reducer - nya
```
function reducer(state = {loading:false, data:null, error:null}, action){
switch(action.type){
  case 'FETCH_SUCCESS':
    return {loading:false, data:action.payload};
  case 'FETCH_ERROR':
    return {loading:false, erorr:action.payload};
  case 'FETCH_LOADING':
    return {loading:true};
default: return state;
}
}
```