# react-context-api

create 3 components

    create new context
    import {createContext} from 'react';
    export const UserContext = createContext();

    import context
    import {UserContext } from "./" 

    Provider
    <UserContext.Provider value={''}>

    </UserContext.Provider>

component context import

    import React,{useContext} from 'react'
    import {UserContext} from './';

    const name = useContext(UserContext)

    dispaly the value

    {name}

pass the Mutilple Value 

    <UserContext.Provider value={{ name: '', email: ''}}>

    </UserContext.Provider>


UseState Component

    import {useState,useEffect} from 'react';

    const [names,SetNames] = useState([])

    useEffect(() => {
      setName(['',''])
    }, [])



    const displayData = names.map((name, index) =>{
      <li key={index}>{name}</li>
    }

    {displayData}


move the state  to app.js

    const [names,SetNames] = useState([])

    useEffect(() => {
      setName(['',''])
    }, [])


    <UserContext.Provider value={{ names: names}}>

    </UserContext.Provider>

change compoent file

    import react, {useContext} from 'react';

    import {UserContext} from './';

    const {names} = useContext(UserContext)

    const displayData = names.map((name, index) =>{
      <li key={index}>{name}</li>
    }

    {displayData}


create Provider

    export function UsersProvider(props){
      const [names,SetNames] = useState([])

    useEffect(() => {
      setName(['',''])
    }, [])
      return(
        <UserContext.Provider value={{names}}>
          {props.childern} 
        </UserContext.Provider >
    )
    }


app js

  <UsersProvider>

  </UsersProvider>
