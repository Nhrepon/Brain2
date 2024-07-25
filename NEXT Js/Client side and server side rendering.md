# Client side rendering

```js
"use client";

import React, { useEffect, useState } from "react";
import 'bootstrap/dist/css/bootstrap.css'; 

const page = () => {
  let [data, setData] = useState([]);
  useEffect(() => {
    (async () => {
      let response = await fetch("https://dummyjson.com/products");
      let json = await response.json();
      setData(json["products"]);
    })();
  }, []);

  return (
    <div className="container">
      <div className="row">
      {data.map((item, i) => {
        return (
          <div key={i} className="col-4 gx-2 gy-2">
            <div className="card m-1">
            <div className="card-body">
              <img className="card-img-top" src={item["images"]} />
              <h2 className="card-title"> {item["title"]}</h2>
              <p className="card-text">{item["price"]}</p>
              <p className="card-text">{item['description']}</p>
            </div>
            </div>
          </div>
        );
      })}
      </div>
    </div>
  );
};

export default page;

```

# Server side rendering

```js
import Image from "next/image";

async function getData() {

  const data = await fetch("https://dummyjson.com/products");

  const json = await data.json();

  return json["products"];

}

  

const page = async () => {

  const data = await getData();

  return (

    <div className="container">

      <div className="row">

        {data.map((item, i) => {

          return (

            <div key={i} className="col-4 gx-2 gy-2">

              <div className="card m-1">

                <div className="card-body">

                  <Image className="card-img-top" src={item["images"]} alt={item["title"]} />

                  <h2 className="card-title"> {item["title"]}</h2>

                  <p className="card-text">{item["price"]}</p>

                  <p className="card-text">{item["description"]}</p>

                </div>

              </div>

            </div>

          );

        })}

      </div>

    </div>

  );

};

export default page;

```


#  a

```js


```

#  a

```js


```

#  a

```js


```

#  a

```js


```

#  a

```js


```

#  a

```js


```

#  a

```js


```
#  a

```js


```

#  a

```js


```
#  a

```js


```
#  a

```js


```
#  a

```js


```
#  a

```js


```
#  a

```js


```

#  a

```js


```