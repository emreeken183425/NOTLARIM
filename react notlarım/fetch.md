
import './App.css';
import {useEffect, useState} from "react"
function App() {
const [countries, setCountries] = useState([])

useEffect(() => {
 # useeffect ile tekrar sayfa render edildikçe döndürdük 
 
<!--  # fetch ile api aldık -->
fetch('https://restcountries.com/v2/all')
<!--  # then ile bir response aldık ve bunun tipini json() yaptık -->
.then(response=>response.json())
<!--  # then ile bir response aldık ve bunun tipini json() yaptık gelen responsu setCountries fonsiyonuna atadık  -->
.then(response=>setCountries(response))  
}, [])

console.log(countries);
  return (
    <div className="App">
     <h1>merhaba</h1>
     <!-- gelen parametremiz olan countries i map ile yazdırdık -->
     {
      countries.map(country=>{
        return <div key={country.name} >
          <img src={country.flag} alt={country.name}  style={{width:"100px"}} />
          <h2>{country.name} </h2>
          <h2>{country.capital}  </h2>
        </div>
      })
     }
    </div>
  );
}

export default App;
