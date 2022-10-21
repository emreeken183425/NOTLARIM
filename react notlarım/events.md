// *                     EVENTS
// * =======================================================

//? ReactJS, Tarayicilar arasi uyumluluk ve performans artisi gibi
//? sebeplerden oturu Sentetik Event olarak adilandirilan Olaylari
//? kullanir. Sentetik Event, aslinda tarayicinin dogal event'larinin
//? bir sarmalayici (Wrapper) arabirimle ortulmesi ile olusur. Bu sayede,
//? React ortaminda kullanilan event'larin bilindik tarayicilarda
//? sorunsuz calismasini saglanir.
//! Ayrinti icin : https://reactjs.org/docs/events.html
<!--Eğer event içinde parametre yoksa direkt olark fonksiyon çağırılır onClick={handleClick} burada fonsksiyonun referansı gönderdik o seben-ble böyle    -->
<!--Eğer event içinde parametre varsa arrow fonksiyon olarak  çağırılır onClick={() => handleClear()} burada fonsiyon içinde fonskiyon çağırdık o sebeple () ekledik  -->
 <!--Eğer event içinde parametre varsa arrow fonksiyon olarak  çağırılır onClick={() => handleClear("cleae btn pressed")} -->
  <!--Eğer event içinde parametre varsa arrow fonksiyon olarak  çağırılır onClick={() => handleClear()} -->
//! info console'da guncellendigini ancak DOM'da guncellenmedigini gorduk.
//* Bunun sebebi REACT'in aksi belirtilmedigi surece elementleri
//* static olarak kabul etmesinden kaynaklanir.

//* React bunu DOM islemlerini minimize etmek icin yapmaktadir.
//* REACT'a hangi elementleri interaktif oldugu belirtilmelidir.
//! React'a elementlerin interaktif oldugunu belirtmek icin state'ler kullanilir.
//! State, elementlerin degisiklik durumlarini tutan nesnelerdir.
//? ReactJs'de state'leri kullanmak icin  2 ayri Component yapisi bulunmaktadir.
//? 1. Statefull Classes (Class Components).
//? 2. Hooks (Functional Components).

//?Biz su ana kadar uygulamalarimizda Fonksiyonel Component'leri kullandik.
//? Yaygin kullanim Fonksiyonel Component'lerdir.



örnek;
const Events = () => {
  const handleClick = () => {
    alert("btn clicked");
  };
  const handleClear = (text) => {
    alert(text);
  };
  return (
    <div>
      <button className="btn btn-warning" onClick={handleClick}>
        Click
      </button>
      <button
        className="btn btn-success m-5 "
        onClick={() => handleClear("cleae btn pressed")}
      >
      
    
        Click 
      </button>
    </div>
  );
};

export default Events;