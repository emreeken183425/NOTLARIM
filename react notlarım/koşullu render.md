```
import './App.css';
import Header from './components/Header';

const isLoggedIn=true;
const fullname="emre eken";

function App() {
 
  return (
    <div className="app">
    {/* isloggedın varsa yoksa ternary yapısı kullandık */}
     {
      isLoggedIn ? "hoş geldiniz" +"  "+ fullname :"giriş yapınız" 
     }
{/* isloggedın varsa  yapısı kullandık */}
{
  isLoggedIn && <div>hoş geldin {fullname} </div>
}
{/* isloggedın yoksa  yapısı kullandık */}
{
   ! isLoggedIn && <a href="#/">giriş yapınız</a>
}
     <Header />
    </div>
  );
}

export default App;

```