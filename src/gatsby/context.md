---
name: Gatsby Context
menu: Gatsby
---

# Context

## Usage

Inject data from top component down to child component without using props 

## API

### createContext


```text
import React, { useContext, createContext, useReducer, useEffect } from 'react'

const { Provider, Consumer } = (CartContext = createContext())
```

the `createContext` return 2 object

1. Provider: wrap the root element
2. Consumer: wrap the element which retrieve the data of context

example 

```text

```

### useContext

```text
import React, { useContext, createContext, useReducer, useEffect } from 'react'

const { addToCart } = useContext(CartContext)
```

this is alternative way using of the Consumer of `createContext`. you dont have to wrap the element to use the context variable, you can just get it by using `useContext` like the above 
