PropsTypes 
props gönderirken propsun tipini belirleriz strin number boolean vs

import Funcitonal from "./components/Funcitonal";
import Navbar from "./components/Navbar";
import User from "./components/User";
import "./styles.css";

export default function App() {
  return (
    <div className="App">
      <Navbar title="User app 3" />
      <User name="emre" salary="5000" departman="Bilişim" />

      <Funcitonal />
    </div>
  );
}


import PropTypes from "prop-types";

const Navbar = (props) => {
  return (
    <div>
      <h1>{props.title} </h1>
    </div>
  );
};
Navbar.PropTypes = {
  title: PropTypes.string.isRequired
};
export default Navbar;


defaul PropTypes ise şöyle 

import Funcitonal from "./components/Funcitonal";
import Navbar from "./components/Navbar";
import User from "./components/User";
import "./styles.css";

export default function App() {
  return (
    <div className="App">
      <Navbar />
      <User name="emre" salary="5000" departman="Bilişim" />

      <Funcitonal />
    </div>
  );
}

navbar page:

import PropTypes from "prop-types";

const Navbar = (props) => {
  return (
    <div>
      <h1>{props.title} </h1>
    </div>
  );
};
Navbar.defaultProps = {
  title: "emre navbar"
};
export default Navbar;

diğer örnek
import Funcitonal from "./components/Funcitonal";
import Navbar from "./components/Navbar";
import User from "./components/User";
import "./styles.css";

export default function App() {
  return (
    <div className="App">
      <Navbar title="User app 3" />
      <User name="emre" departman="Bilişim" />

      <Funcitonal />
    </div>
  );
}

import { Component } from "react";
import PropTypes from "prop-types";
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
User.defaultProps = {
  name: "bilgi yok",
  salary: "bilgi yok",
  departman: "bilgi yok"
};
User.PropTypes = {
  name: PropTypes.string.isRequired,
  salary: PropTypes.string.isRequired,
  departman: PropTypes.string.isRequired
};
export default User;
