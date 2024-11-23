
```js
const message = userInput ?? "Default message";

item?.map((item, i) => {  
    return (  
        <>  
            <li key={i} className="nav-item bg-light p-2 rounded">  
                <a className="nav-link" href={item.href}>{item.name}</a>  
            </li>        </>    )  
})





```


