// import React, { useEffect, useState } from 'react'
// import axios from "axios"
// const Card = () => {

// const [country, setCountry] = useState([])

// useEffect(() => {
//   // get post hangisini istiyorsak onu yazıyoruz axios yanına
//   axios.get('https://restcountries.com/v2/all')
//   .then(response=>setCountry(response))
// }, [])


//   return (
//     <div>
//       <h1>merhaba</h1>
//       {country.map((emre) => {
//         return (
          
//            <div  key={emre.name} className="container mt-3">
          
//           <div className="map" >
//           <div className="container d-flex  mt-3" >
//               <div className="card">
//                   <img className="card-img-top  width:150px "
//                       src={emre.flags.png} 
//                       alt={emre.name.common} />
//                   <div className="card-body ">
//                       <h1 className="card-title">Country:{emre.name} </h1>
//                       <h3 className="card-text">Capital:{emre.capital} </h3>
//                       <h4 className="card-text">Population:{emre.population}</h4>                      
//                   </div>
//               </div>
//           </div>
//           </div>
//           </div>
     
              


// export default Card

```
import React, { useEffect, useState } from 'react'
import axios from "axios"
function Axios() {
    const [users, setUsers] = useState([])
const [loading, setLoading] = useState(true)
    useEffect(() => {
      axios('https://jsonplaceholder.typicode.com/users')
      .then(res=>setUsers(res.data))
      .finally(()=>setLoading(false))
    }, [])
    
  return (
    <div>
<h1>axios ile veri çekme </h1>

{loading && <div>yükleniyor...</div> }
{
    users.map(user=>(
        <ul key={user.id} >
            <li>{user.name} </li>
            <li>{user.address.street} </li>
            <li>{user.company.name} </li>
        </ul>
    ) )
}

    </div>
  )
}

export default Axios
```