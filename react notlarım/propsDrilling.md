App js

import Navbar from "./Navbar";
import { Component } from "react";
import Users from "./Users";
import Kullanıcı from "./Kullanıcı";
import Karısık from "./Karısık";

class App extends Component {
  state = {
    users: [
      {
        id: 1,
        name: "ersin",
        salary: "5000",
        department: "bilişim"
      },
      {
        id: 2,
        name: "mehmet",
        salary: "5000",
        department: "magazin"
      },
      {
        id: 3,
        name: "habip",
        salary: "5000",
        department: "haberler"
      },
      {
        id: 4,
        name: "ahmet",
        salary: "5000",
        department: "spor"
      }
    ],
    kullanıcı: [
      {
        id: 1,
        name: "ali",
        salary: "5000",
        department: "bilişim"
      },
      {
        id: 2,
        name: "veli",
        salary: "5000",
        department: "magazin"
      },
      {
        id: 3,
        name: "deli",
        salary: "5000",
        department: "haberler"
      },
      {
        id: 4,
        name: "emre",
        salary: "5000",
        department: "spor"
      }
    ]
  };

  render() {
    return (
      <div className=" App row d-flex ">
        <div className="d-flex col-md-3">
          <Navbar title="User app 3" />
          <Users users={this.state.users} />
          <Kullanıcı kullan={this.state.kullanıcı} />
          <Karısık opera={this.state.users} />
        </div>
      </div>
    );
  }
}
export default App;

Kullanıcı sayfası 
import { Component } from "react";
import User from "./User";

class Kullanıcı extends Component {
  render() {
    const { kullan } = this.props;
    console.log(kullan);

    return (
      <div>
        <h1>Kullanıcı sayfası</h1>
        {kullan.map((mert) => {
          return (
            <User
              key={mert.id}
              name={mert.name}
              salary={mert.salary}
              department={mert.department}
            />
          );
        })}
      </div>
    );
  }
}
export default Kullanıcı;

Users sayfası 

import { Component } from "react";
import User from "./User";
class Users extends Component {
  render() {
    const { users } = this.props;
    console.log(users);

    return (
      <div>
        {users.map((user) => {
          return (
            <User
              key={user.id}
              name={user.name}
              salary={user.salary}
              department={user.department}
            />
          );
        })}
      </div>
    );
  }
}
export default Users;

 User sayfası
 import { Component } from "react";
import PropTypes from "prop-types";
class User extends Component {
  render() {
    // THİS.PROPS LARLA UĞRAŞMAK İSTEMİYORSAK DESTRUCTİNG YÖNTEMİ KULLANIRIZ ODA AŞAĞIDAKİ GİBİ
    const { name, department, salary } = this.props;
    return (
      <div>
        <ul>
          <li>ad:{name} </li>
          <li>departman:{department} </li>
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

export default User;

