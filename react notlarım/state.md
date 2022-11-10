
import User from "./User";
import Navbar from "./Navbar";
export default function App() { 
  return (
    <div className="App">
      <Navbar title="User app 3" />
      <User name="emre" departman="Bilişim" />
    </div>
  );
}


import { Component } from "react";
import PropTypes from "prop-types";
class User extends Component {
  <!-- constructor(props) {
    super(props);
    this.state = {
      isVisible: false
    };
  } -->

  render() {
    // THİS.PROPS LARLA UĞRAŞMAK İSTEMİYORSAK DESTRUCTİNG YÖNTEMİ KULLANIRIZ ODA AŞAĞIDAKİ GİBİ
    const { name, departman, salary } = this.props;
    const { isVisible } = this.state;
    return (
      <div className="col-md-8 mb-4">
        <div className="card">
          <div className="card-header d-flex justify-content-center">
            <h4 className="d-inline">{name} </h4>
            <i className="far fa-trash-alt"></i>
          </div>
          {isVisible ? (
            <div className="card-body">
              <p className="card-text">Maaş:{salary} </p>
              <p className="card-text">Departmant:{departman} </p>
            </div>
          ) : null}
        </div>
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
