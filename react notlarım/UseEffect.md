//?========================================================
//?                  USEEFFECT HOOK
//?========================================================
//! UseEffect Hook'u fonksiyonel componenler'te yan etkileri
//! (side effect) gerceklestirmek icin kullanilir.
//! componentDidMount,componentDidUpdate,ve componentWillUnmount
//! metotlarinin bir birlesimi gibi dusunulebilir.

```
import React, { useState, useEffect } from "react";

const Functionstate = () => {
  const [counter, setCounter] = useState(0);
  const [counter2, setCounter2] = useState(0);
  //  useState burada 2 değer alır counter değer setCounter ise fonksiyon
  useEffect(() => {
    console.log("useEffect");
  }, []); 
  // [] içi boş olması demek bir kere çalıştır demek içine [counter ]
  // [counter] olursa counter her değiştiğinde useEffect içindeki fonksiyon çağrılır
  // [counter,counter2] olursa counter her değiştiğinde useEffect içindeki fonksiyon çağrılır

  const increase = () => {
    setCounter(counter + 1);
  };
  const descrise = () => {
    setCounter(counter - 1);
  };
  return (
    <div>
      <h1>function Component</h1>
      <p>counter:{counter} </p>
      <p>counter2:{counter2} </p>
      <button onClick={() => increase()}>INC</button>
      <button onClick={() => setCounter2(counter2 + 1)}>counter2</button>
      <button onClick={() => descrise()}>DESC</button>
    </div>
  );
};

export default Functionstate;
```

//?========================================================
//?                  USEEFFECT HOOK
//?========================================================
//! UseEffect Hook'u fonksiyonel componenler'te yan etkileri
//! (side effect) gerceklestirmek icin kullanilir.
//! componentDidMount,componentDidUpdate,ve componentWillUnmount
//! metotlarinin bir birlesimi gibi dusunulebilir.
 //? https://reactjs.org/docs/hooks-reference.html#usestate
  //! State degiskeninin degeri, 1.render ile initialState
  //! parametresinin ilk degerini alir. Dolayisiyle bu durumda
  //! prop'tan gelen ilk deger state'e aktarilir.
  //! Sonradan degisen props degerleri useState'e aktarilmaz.
  //! Eger props'tan gelen degerleri her degisimde useState'e
  //! aktarmak istersek useEffect hook'unu componentDidUpdate
  //! gibi kullanabiriz.

  //? componentDidUpdate
  //? newTitle veya description her degistiginde local title ve
  //? desc state'lerimizi gunceliyoruz.

import { useState, useEffect } from 'react';

//! useEffect(() => {
//*   /* ComponentDidMount code */
//! }, []);

//! useEffect(() => {
//*   */ componentDidUpdate code */
//! }, [var1, var2]);

//! useEffect(() => {
//!   return () => {
//*     //* componentWillUnmount code */
//!   };
//! }, []);

//! useEffect(() => {
//*   //* componentDidMount code + componentDidUpdate code */

//!   return () => {
//*     //* componentWillUnmount code */
//!   };
//! }, [var1, var2]);

const UseEffectHook = () => {
  const [count, setCount] = useState(0);

  //! ComponentDidMount
  // useEffect(() => {
  //   console.log('Mounted'); //! fetch, asyn-await ,localStorage, setTimeout
  //   setTimeout(() => {
  //     alert('Data Fetched');
  //   }, 3000);
  // },[]);

  //! ComponentDidMount + componentDidUpdate
  // useEffect(() => {
  //   console.log('Mounted + Updated');
  //   setTimeout(() => {
  //     alert('Data Fetched');
  //   }, 1000);
  // }, [count]);

  //! ComponentDidMount + componentWillUnmount
  const fetchData = () => {
    console.log('Data Fetched');
  };

  useEffect(() => {
    //! ComponentDidMount
    const timerId = setInterval(fetchData, 1000);
    console.log('Mounted');
    return () => {
      //! componentWillUnmount
      clearInterval(timerId);
      console.log('Unmounted');
    };
  }, []);

  console.log('rendered');
  return (
    <div className="container text-center mt-4">
      <h1 className="text-danger">USEEFFECT</h1>
      <h3>Count:{count}</h3>
      <button className="btn btn-warning" onClick={() => setCount(count + 1)}>
        INC
      </button>
    </div>
  );
};

export default UseEffectHook;
