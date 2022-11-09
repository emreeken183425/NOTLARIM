
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
