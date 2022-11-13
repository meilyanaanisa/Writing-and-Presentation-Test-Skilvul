# Rangkuman Minggu ke-Delapan Skilvul

## React-Context
Sebuah cara untuk mengirimkan data tanpa menggunakan props disetiap components.

### Kapan menggunakan react-context ?
Context dirancang untuk berbagi data yang dianggap global, seperti pengguna terotentikasi saat ini tema, atau bahasa yang digunakan. Misal seperti contoh dibawah memasang prop theme untuk memberikan style pada komponen button
```
class App extends React.Component {
  render() {
    return <Toolbar theme="dark" />;
  }
}

function Toolbar(props) {
    return (
    <div>
      <ThemedButton theme={props.theme} />
    </div>
  );
}

class ThemedButton extends React.Component {
  render() {
    return <Button theme={this.props.theme} />;
  }
}
```

- memulai context dengan membuat function createContext
- en sebagai nilai default
- createContext mengembalikan fungsi provider dan consumer component
```
export const LocaleContext = React.createContext('en')
```

### Api Context React
- Struktur komponen yang dapat dibagi ke semua level aplikasi. Tujuan utama adalah untuk memecahkan masalah prop  

### Context.Provider
- Sebuah komponen yang memberikan perubahan terhadap konsumsi komponen

```
import React from 'react';

export const LocaleContext = React.createContext();

class LocaleProvider extends React.Component {
  constructor(props) {
    super(props);

    this.changeLocale = () => {
      this.setState(state => {
        const newLocale = state.locale === 'en' ? 'fr' : 'en';
        return {
          locale: newLocale
        };
      });
    };

    this.state = {
      locale: 'en',
      changeLocale: this.changeLocale
    };
  }

  render() {
    return (
      <LocaleContext.Provider value={this.state}>
        {this.props.children}
      </LocaleContext.Provider>
    );
  }
}

export default LocaleProvider;
```

### Context Konsumer
- Komponen yang mengalami perubahan konteks, meminta data melalui provider.
```
import React from 'react';

import { LocaleContext } from './context/LocaleContext';

export default () => {
  return (
    <LocaleContext.Consumer>
      {localeVal =>
        localeVal.locale === 'en' ? <h1>Welcome!</h1> : <h1>Bienvenue!</h1>
      }
    </LocaleContext.Consumer>
  );
};
```

### Class.contextType
- Digunakan untuk menetapkan objek konteks


## React-Testing
Pengcheckan setiap komponent apakah terjadi bug atau tidak, tanpa harus menguji implementasi detail dari komponent.

Membangun DOM Testing Library dengan menambahkan API untuk bekerja dengan react components. 

- install testing
```
npm install --save-dev @testing-library/react
```

- install jest
melakukan testing pada JavaScript.
```
npm install --save-dev jet
```

- install jest DOM
```
npm install --save-dev @testing-library/jest-dom
```

- Lakukan import kedalam project
```
import "@testing-library/jest-dom/extend-expect";
```

- Melakukan testing dan setup di dalam jest.config.js
```
module.exports = {
  setupFilesAfterEnv: ["@testing-library/jest-dom/extend-expect"],
};
```

- Membuat Test
```
import React from "react";
import { render } from "@testing-library/react";
import App from "./App";

test("renders react", () => {
  const { getByText } = render(<App />);
  const context = getByText(/learn react/i);
  expect(context).toBeInTheDocument();
});
```