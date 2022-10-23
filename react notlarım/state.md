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

 ******useState*****
//* useState en cok kullanilan Hook'tur.
  //* Bir state'in degisken, dizi ve obje ile kullanilabilmesine olanak saglar

******CLASS COMPONENTS'DE STATE*******
```
import React from "react";

class ClassComponent extends React.Component {
  render() {
    return (
      <div>
        <h1>Clas Component</h1>
      </div>
    );
  }
}

export default ClassComponent;


```
```
import React from "react";

const Functionstate = () => {
  return (
    <div>
      <h1>function Component</h1>
    </div>
  );
};

export default Functionstate;

```

