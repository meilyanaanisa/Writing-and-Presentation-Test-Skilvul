# Rangkuman Materi Minggu ke-6 di Skilvul

## Reactjs

- React js dibuat oleh Jordan Walke Seorang Tim Engineer Facebook.
- React js bukanlah sebuah framework melainkan library JavaScript untuk membuat tampilan User Interface pada web browser.
- Konsep modular JavaScript pada Reactjs dimana membagi 1 tampilan pada website menjadi komponen-komponen kecil.
- Salah satu konsep react yaitu learn one, write anywhere. kita hanya perlu membuatnya sekali dan dapat dipanggil berkali kali.
- Hal yang harus disiapkan sebelum menggunakan Reactjs yaitu menginstall [Node Js](https://nodejs.org "Link Nodejs"), agar dapat menginstall package yang sudah disediakan oleh JavaScript.
- Pilih Versi LTS
![NodeJs!](lts.png "download versi lts")
- Lalu lakukan installation seperti biasa setelah di download
- Untuk mengetahui apakah sudah berhasil install di gitbash.
> node -v
- Check versi npm
> npm -v
- Menggunakan Library 
> npx create-react-app my-app
- Proses berhasil unduh react akan tampil seperti ini.
![React!](react-berhasil.jpeg "install react berhasil")
- Tampilan workspace react.js yang telah diinstall.
![Record!](workspace.jpeg "workspace react")
- Menjalankan react ke web browser
> npm start
- Sudah mauk ke tahap deployment web
> npm run build
- Tag HTML di dalam JavaScript disebut dengan jsx.
- Development dilakukan di dalam folder src.
- Setiap jsx hanya bisa memiliki satu parent element atau pembungkus element. 
- Gunakan tag div atau tag fragment kosong sebagai pembungkusnya.
- Dengan menggunakan react saat update data maka hanya melakukan render ulang pada komponen tersebut sehingga menjadi lebih cepat dalam performance.
- Atribute class pada jx harus menggunakan className.

```
import React from 'react';

function perkenalan (){
    return{
        <div>
        <h1 className="tittle>Selamat Datang</h1>
        <p className="description>Ini adalah website pertama menggunakan reactjs</p>
        </div>
    }
}

export default perkenalan;
```

- Menyelipkan syntax JavaScript ke dalam jsx menggunakan curly braces {}.

```
import React from 'react';

function perkenalan (){
    return{
        <div>
        <h1>{1 + 2}</h1>
        </div>
    }
}

export default perkenalan;
```
- Akses variabel menggunakan curly braces
```
import React from 'react';

function perkenalan (){
    const nama = 'meilyana'
    return{
        <div>
        <h1>{nama}</h1>
        <p>{nama.lowerUpperCase</p>
        </div>
    }
}

export default perkenalan;
```
## Component 

- Component adalah salah satu core React Js yang dapat membagi UI dalam satuan-satuan kecil.
- Misal : didalam HTML terdapat navbar, form, text title. Mereka disebut component
- Ada dua cara membuat component

  - Gunakan function
  - Gunakan class

- State dan Props adalah hal yang berhubungan dengan Stateless dan Stateful Component
- Stateless berarti tidak memiliki State. Dia hanya memiliki props.

```
const Member = (props, nameColor) => {
  
    return(
    <div className="container">
        
    <div className='com-profile'>
        <h1>Profile</h1>
            <div className="picture-profile" >
                <img src="https://ps.w.org/metronet-profile-picture/assets/icon-128x128.png?rev=2464419" alt="" className='profil-picture'/>
            <div className="ket-profile">
                <h3 style={{ color: nameColor}}>{props.name}</h3>
                 <p>{props.age}</p>
                <p>{props.info}</p>
            </div>
            </div>
        </div>
    </div>
    );
}

export default Member;
```
- Stateful berarti memiliki state dan bisa mengirim tersebut ke component.
```
import './App.css';
import Member from './component/Member.jsx';

function App() {
  return (
      <div
      <Member name={'Putri Ramadani'} age={'16'} info={'Siswi SMP'} nameColor={"yellow"}/>

      <Member name={'Meilyana Anisa Mawarti'} age={'22'} info={'Mahasiswi'}/>
      </div>
  );
}

export default App;
```
- Jadi state adalah data lokal
- Props digunakan agar component memiliki data yang dinamis yang dikirim dari component lain.

- UseState: penyimpanan data yang berubah - ubah
> const [name, setName] = useState("Meilyana");

## React Js Hooks

- Hooks adalah fitur baru yang baru dikenalkan di ReactJs pada tahun 2018.

- Hooks bertujuan untuk memudahkan penggunaan functional components agar bisa menggunakan state, dan lifecycle lainnya.

- Hooks yang sering digunakan adalah useState dan useEffect dua hal ini sama dengan state dan lifecycle di class yang biasa kita sering gunakan.

- Mount, memunculkan tampilan.
- Unmount, menghilangkan tampilan
- Update, terjadi perubahan pada data
- useeffect memberikan effect samping di dalam life cycle

**Perbedaan functional component dengan class component.**

- Class Component
```
class component extends React.Component {
    constructor(props){
        super(props);
        this.state = { nama : "Meilyana"};
    }
    render(){
        return <h1>Hallo,{this.state.nama}</h1>
    }
}
```
- Functional Component
```
import { useState } from "react";

function App() {
    const [nama, setNama] = useState("Meilyana");

    return <h1>Halo, {nama}</h1>;
}
```
- Kelebihan Penggunaan Hooks

Penggunaan hook sangat di rekomendasikan dikarenakan penggunaan hook lebih mudah dimenegerti serta code jauh lebih clean, pendek dan mudah dimengerti

- Pengertian useState

pengertian useState sendiri sama seperti state biasa yang membedakan penggunaan useState berbeda dengan setState/state di class component.

- useState syntac structure
 > const [nama, setnama] = useState ("Meilyana");

- Penggunaan useState
```
import { useState } from "react";

function App() {
    const [nama, setNama] = useState("Meilyana");

    return(
        <>
        <p>Halo, saya{nama}</p>
        <button onClick={() => setNama("Intan")}></button>

        </>
    )
}
```
- Array dalam useState Hooks

Menggunakan tanda [] dalam useState untuk menandakan bahwa state tersebut merupakan array
> const [nama, setnama] = useState ([]);

- Penggunaan useState hooks

useState, biasanya akan digunakan saat kamu menyimpan data suatu form yang nantinya akan di post ke api untuk diproses

dan kita dapat melakukan call api, kita bisa menyimpan data hasil get dari api tersebut kedalam state menggunakan useState

- Pengertian useEffect hooks

hooks yang bisa digunakan untuk menggunakan lifecycle pada functional component dengan mudah.

- Pengertian lifecycle

proses perulangan data di dalam komponen yang menyatukan componentDidMount, componentDidUpdate, dan componentWillUnmount.

- Penggunaan useEffect

Dapat dilakukan sebelum render, useEffect sendiri biasanya ditempatkan dibawah useState.

useEffect akan dijalankan setiap component baru di mount ( componentDidMount ), terjadi perubahan ( componentDidUpdate ), dan pada saat component akan ditinggalkan ( componentWillUnmount )

**Penggunaan useEffect**

```
import { useEffect, useState } from "react";

function App() {
    const [nama, setNama] = useState(true);


    useEffect(() => {
        console.log("ada perubahan");

    }, [nama]);

    return (
        <>
        <h1>Perubahan : {nama}</h1>;
        <button onClick={() => setNama (!nama)}>Ubah</button>
        </>
     )
}
```

- Menghindari re-render yang berlebihan

Menambahkan [] atau [**variabelYangBerubah**] untuk menentukan bahwa useEffect berjalan saat terjadi update

- Penggunaan useEffect hooks

Pada saat penggunaan suatu call api, karena api akan selalu dipanggil saat komponen terbentuk, maka call api bisa dilakukan didalam useEffect