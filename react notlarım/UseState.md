//* ============================ CLASS COMPONENTS AND STATE ============================
//* React'da Class-Component'ler ES6 class yapisina dayanmaktadir.
//* Cok fazla boilerplate kod icermektedir.
//* Ancak Class-Component'ler React'da state'leri barindiran ilk component yapisidir.
//* State, aslinda bir component hakkinda bilgi tutan bir React nesnesidir.
//* Bir componentin state'i zaman icerisinde degisebilir.
//* State her degistiginde React bu componenti yeninden render eder.
//* Bir state'e baslangıc degeri constructor metodu icersinde this.state ile atanabilir
//* constructor'in disinda state, setState() metodu ile degistilebilir.
//* 
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
 ******useState*****
//* useState en cok kullanilan Hook'tur.
  //* Bir state'in degisken, dizi ve obje ile kullanilabilmesine olanak saglar

******CLASS COMPONENTS'DE STATE*******
```
import React from "react";

class ClassComponent extends React.Component {
  constructor() {
    super();
    this.state = {
      counter: 0
    };
  }

  increase = () => {
    this.setState({ counter: this.state.counter + 1 });
  };
  descrise = () => {
    this.setState({ counter: this.state.counter - 1 });
  };

  render() {
    console.log("class Components  ", this.state.counter.counter);

    return (
      <div>
        <h1>Clas Component</h1>
        <p>Counter:{this.state.counter} </p>
        <button onClick={() => this.increase()}>İNC</button>
        <button onClick={() => this.descrise()}>DESC</button>
      </div>
    );
  }
}

export default ClassComponent;


```
```
const Functionstate = () => {
  const [counter, setCounter] = useState(0);
  //  useState burada 2 değer alır counter değer setCounter ise fonksiyon
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
      <button onClick={() => increase()}>INC</button>
      <button onClick={() => descrise()}>DESC</button>
    </div>
  );
};

export default Functionstate;

```

import React, { useState } from "react";

const UseStateHook = () => {
  const [count, setCount] = useState(4);
  function increase() {
    setCount(count + 1);
  }
  function decrease() {
    setCount(count - 1);
  }
  return (
    <div>
      <button onClick={decrease} className="btn-btn-primary">
        -
      </button>
      <span>{count} </span>
      <button onClick={increase} className="btn-btn-warning">
        +
      </button>
    </div>
  );
};

export default UseStateHook;