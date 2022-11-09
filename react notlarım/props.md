FUNCTİONAL COMPONENTSTE PROPS
Props kullanımı nasıl olur*
örneğin biz User bilgilerini navbara göndereceksek props kullanırız bunun için şöyle yaparız:
navbar yanına bir key yazılır ve bu key navbar componenttinde çağrılır
title="User app" burada title keyimiz ve = ise atadığımız isim 


 import Funcitonal from "./components/Funcitonal";
import Navbar from "./components/Navbar";
import User from "./components/User";
import "./styles.css";

export default function App() {
  return (
    <div className="App">
      <Navbar  title="User app" />
       <User />
      <Funcitonal />
    </div>
  );
}

navbar sayfasında çağrılır aşağıdaki gibi

const Navbar = (props) => {
  return (
    <div>
      <h1>{props.title} </h1>
    </div>
  );
};
export default Navbar;


CLASS COMPONENTSTE PROPS

import Funcitonal from "./components/Funcitonal";
import Navbar from "./components/Navbar";
import User from "./components/User";
import "./styles.css";

export default function App() {
  return (
    <div className="App">
      <Navbar title="User app 2" />
      <User name="emre" salary="5000" departman="Bilişim" />

      <Funcitonal />
    </div>
  );
}
 USER DA ÇAĞIRMA ŞEKLİ AŞAĞIDA 
 import { Component } from "react";

class User extends Component {
  render() {
    return (
      <div>
        <ul>
          <li>ad:{this.props.name} </li>
          <li>departman:{this.props.departman} </li>
          <li>Maaş: {this.props.salary}</li>
        </ul>
      </div>
    );
  }
}
export default User;

import { Component } from "react";

class User extends Component {
  render() {
    // THİS.PROPS LARLA UĞRAŞMAK İSTEMİYORSAK DESTRUCTİNG YÖNTEMİ KULLANIRIZ ODA AŞAĞIDAKİ GİBİ
    const { name, departman, salary } = this.props;
    return (
      <div>
        <ul>
          <li>ad:{name} </li>
          <li>departman:{departman} </li>
          <li>Maaş: {salary}</li>
        </ul>
      </div>
    );
  }
}
export default User;
