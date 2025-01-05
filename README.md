# Axios

Created: December 23, 2024 5:12 PM

# Documentation

[Getting Started | Axios Docs](https://axios-http.com/docs/intro)

# Data fetching

Without Axios

```jsx
import { useState, useEffect } from "react";
const Phones = () => {
    const [phones, setPhones] = useState([]);
    useEffect(() => {
        fetch('https://openapi.programming-hero.com/api/phones?search=iphone')
           .then(response => response.json())
           .then(data => setPhones(data.data));
    }, []);
    console.log(phones);
    return (
        <div>
            <h3>Phones: {phones.length}</h3>
        </div>
    );
};

export default Phones;
```

With Axios

```jsx
import axios from "axios";
import { useState, useEffect } from "react";
const Phones = () => {
    const [phones, setPhones] = useState([]);
    useEffect(() => {
        axios.get('https://openapi.programming-hero.com/api/phones?search=iphone')
           .then(response => setPhones(response.data.data))
    }, []);
    return (
        <div>
            <h3>Phones: {phones.length}</h3>
        </div>
    );
};

export default Phones;
```

Demo project

[https://github.com/HiYasin/Axios](https://github.com/HiYasin/Axios)

# API Calling

API call in POST method using fetch().

```jsx
fetch('http://localhost:5000/user',{
	method: 'POST',
	headers: {
		'content-type': 'application/json'
	},
	body: JSON.stringify(loginInfo)
})
.then(res => res.json())
.then(data => {
  console.log(data.insertedId);
  alert('User successfully added');
  event.target.reset();
});
```

API call in POST method using axios.

```jsx
axios.post('http://localhost:5000/user', user)
.then(res => {
  console.log(res.data.insertedId);
  alert('User successfully added');
  event.target.reset();
});
```

# Create axios instance as react hook for API call

1. Create custom hook for axios.
    
    `useAxiosSecure.jsx`
    
    ```jsx
    import axios from 'axios';
    
    const axiosInstance = axios.create({
        baseURL: 'http://localhost:5000', // Replace with your API base URL
        withCredentials: true,
    });
    const useAxiosSecure = () => {
        return axiosInstance;
    };
    
    export default useAxiosSecure;
    ```
    
2. Use custom hook. Don’t forget to import before use.
    
    ```jsx
    useEffect(()=>{
    //using conventional fetch
    	fetch(`http://localhost:5000/job-posts?email=${user.email}`,
    	{credentials: 'include'})
    	.then(res => res.json())
    	.then(data => setJobs(data))
    	.catch(err => console.log(err));
    
    //using axios interceptor
    	axios.get(`http://localhost:5000/job-posts?email=${user.email}`,
    	{withCredentials: true})
    	.then(res => setJobs(res.data))
    	.catch(err => console.log(err.response));
    	
    //using useAxiosSecure custom hook
    	axiosSecure.get(`/job-posts?email=${user.email}`)
    	.then(res => setJobs(res.data))
    	.catch(err => console.log(err.response));
    }, []);
    ```
    

# Axios interceptor

Make secure axios instance to block unauthorized access using axios interceptor.

```jsx

import axios from 'axios';
import { useContext, useEffect } from 'react';
import { AuthContext } from '../context/AuthProvider';
import { useNavigate } from 'react-router-dom';

const axiosInstance = axios.create({
    baseURL: 'http://localhost:5000', // Replace with your API base URL
    withCredentials: true,
});
const useAxiosSecure = () => {
    const { signOutUser } = useContext(AuthContext);
    const navigate = useNavigate();

    useEffect(()=>{
        axiosInstance.interceptors.request(
            reponse => reponse,
            error => {
                if( error.status === 401 || error.status === 403){
                    signOutUser()
                    .then(()=>{
                        navigate('/login');
                    })
                    .catch(err => console.log(err));
                    
                }
                return Promise.reject(error);
            }
        );
    }, [])

    return axiosInstance;
};

export default useAxiosSecure;
```