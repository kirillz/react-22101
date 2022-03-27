
# 🚀 О проекте react-22101

В этом проекте мы пошагово создадим React приложение которое решит игровые задачи по информатике и продемонстрирует их вконце в вашем приложении написанном вами собственноручно. Файловая структура уже создана для нас, но функционал еще нет или он не работает, следуя инструкциям пошагово по задачам вы напишите код и сами поймете как работает тот или иной код в React. В конце этого проекта у вас появится видение как работать с:

- Components (Компонентами)
- State (Стейтом)
- Import / Export (Импортом и Экспортом)
- .gitignore (для чего нужен файл)
- NPM (как устанавливать npm пакеты)
- JSON.stringify

📝Попробуйте не заглядывать в решение не сделав сами задачу.   
Помните, каждая написанная строка кода развивает вашу мышечную память!   
Поехали... :)  

# Конечный результат который вы получите

![1-2](https://user-images.githubusercontent.com/1161809/160261052-abd654d4-8f06-4f6d-99ab-ca2d509d6776.png)

## Установка

- `Fork` или `clone` этот репозиторий к себе на комп. `git clone https://github.com/kirillz/react-22101.git`
- `cd` в директорию с проектом.
- Запустите команду `npm install` или `npm i` или `yarn install` в зависимости от предпочтений.
- Затем когда `npm install` завершит работу, запустите `npm start` или `yarn start` .

## Шаг 1

### Описание шага

На этом этапе мы собираемся погрузиться в функциональность приложения. Если мы заглянем в папку `src`, то увидим, что у нас есть папка `components` с `TopicBrowser` и папкой `Topics`. Наш компонент `TopicBrowser` будет отображать список тем из папки `Topics`. Каждая тема будет отдельным компонентом.

### Инструктаж

- Откройте `src/components/TopicBrowser/TopicBrowser.js`.
- Импортируйте `React` и `Component` из модуля `react`.
- Создайте базовый компонет на основе класса `TopicBrowser`:
  - Пусть этот компонент делает `render` одного тэга `<p>` внутри которого будет надпись "Hello World."
- Экспортируйте `TopicBrowser` by default (по-умолчанию).
- Откройте `src/App.js`.
- Импортируйте `TopicBrowser` компонент после строки `import` react.
- Отрендерьте `TopicBrowser` компонент в `render` методе в `App`.

<details>

<summary> Детальные объяснения каждой инструкции :construction: </summary>

<br />

Начнем с того что откроем `src/components/TopicBrowser/TopicBrowser.js` и импортируем `React, { Component }` from `react` в самом начале файла. Это позволит нам использовать JSX и создать класс который расширяется(extends) от `Component`.

```js
import React, { Component } from "react";
```

Теперь давайте создадим базовый компонент, который отображает элемент `<p>` с надписью «Hello World». Мы сделаем это, записав `class TopicBrowser extends Component {}`. TopicBrowser — это имя класса, которое может быть любым, каким вы хотите, обычно при работе с классами используется регистр CamelCase (это означает, что первая буква названия классов также пишется с заглавной буквы). В конструкторе React для имени вашего класса требуется CamelCase. Если этого не сделать то, компонент не будет монтироваться или отображаться в вашем приложении. Поскольку этот компонент будет просматривать наши темы(Topics), я выбрал имя класса TopicBrowser.

```js
class TopicBrowser extends Component {}
```

Теперь, когда у нас есть компонент `TopicBrowser`, давайте заставим его отображать элемент `<p>`. Поскольку мы расширили `Component`, у нас есть доступ к методу `render() {}`. Это метод, который вызывается для рендеринга нашего JSX в DOM. Внутри метода `render` мы используем оператор return для `возврата` JSX, который будет отображаться.

```js
class TopicBrowser extends Component {
  render() {
    return <p> Hello World </p>;
  }
}
```

Затем нам нужно произвести `export` нашего компонента `TopicBrowser`, чтобы другие файлы могли делать его `import`. Возможно, вы видели два разных способа выполнения этого метода. Один из способов — экспортировать его в конец файла, а другой — в той же строке, что и при объявлении класса.

<details>

<summary> <code> TopicBrowser.js ( export внизу файла ) </code> </summary>

```js
import React, { Component } from "react";

class TopicBrowser extends Component {
  render() {
    return <p> Hello World </p>;
  }
}

export default TopicBrowser;
```

</details>

<details>

<summary> <code> TopicBrowser.js ( export в той же строке ) </code> </summary>

```js
import React, { Component } from "react";

export default class TopicBrowser extends Component {
  render() {
    return <p> Hello World </p>;
  }
}
```

</details>

<br />

Оба вышеприведенных способа вполне хороши, однако я буду использовать одну и ту же строку `export`. Теперь, когда наш `export` настроен, мы можем «импортировать» его через `import` в «App.js» и «рендерить» `render`. Мы можем сделать `import` компонента в следующем формате: `import ComponentNameHere from '/file_path_to_component_here'`. Поэтому наш `import` в коде `src/components/App.js` должен будет выглядеть сейчас так:

```js
import TopicBrowser from "./components/TopicBrowser/TopicBrowser";
```

Наш `import` достаточно умен, чтобы добавить для нас расширение «.js». Теперь, когда в `src/components/App.js` импортирован `TopicBrowser`, мы можем сделать его `render` так же, как рендерили наш элемент `<p>` в `TopicBrowser`. Единственное отличие заключается в том, что для `рендеринга` компонентов вы заключаете имя компонента в `< />`. Наш `src/components/App.js` теперь должен выглядеть так:

```js
import React, { Component } from "react";
import "./index.css";
import TopicBrowser from "./components/TopicBrowser/TopicBrowser";

class App extends Component {
  render() {
    return <TopicBrowser />;
  }
}

export default App;
```

</details>

## Решение

<details>

<summary> <code> App.js </code> </summary>

```js
import React, { Component } from "react";
import "./index.css";
import TopicBrowser from "./components/TopicBrowser/TopicBrowser";

class App extends Component {
  render() {
    return <TopicBrowser />;
  }
}

export default App;
```

</details>

<details>

<summary> <code> TopicBrowser.js </code> </summary>

```js
import React, { Component } from "react";

export default class TopicBrowser extends Component {
  render() {
    return <p> Hello World </p>;
  }
}
```

</details>

![2-2](https://user-images.githubusercontent.com/1161809/160261144-deed3b54-4370-434c-b69c-d09aa10fcd7c.png)

## Шаг 2

### Описание шага

На этом шаге мы визуализируем все наши темы из папки `Topics`, создадим базовые схемы для каждой из тем (точно так же, как мы делали `TopicBrowser`), с той лишь разницей, что `<p>` станет содержать указание имени компонента, а затем импортировать и визуализировать эти компоненты темы в наш компонент `TopicBrowser`.

### Инструктаж

- Создайте базовую схему для каждого компонента темы (точно так же, как мы делали компонент `TopicBrowser`):
  - Убедитесь, что имя класса совпадает с именем файла.
  - Пусть компонент отображает элемент `<p>`, отображающий имя компонента.
- Откройте `src/components/TopicBrowser/TopicBrowser.js`.
- Импортируйте все файлы тем из `src/components/Topics` в `src/components/TopicBrowser/TopicBrowser.js`.
- Визуализируйте родительский элемент `div`, содержащий все компоненты Topic.

<details>

<summary> Детальные описание инструкций шага :construction: </summary>

<br />

Начнем с того, что зайдем в папку «Темы». Внутри мы увидим 5 javascript-файлов, внутри этих файлов мы создадим React-компонент, решающий некую компьютерную игрушку. Базовая схема будет одинаковой для всех этих компонентов, с той лишь разницей, что элемент `<p>` будет визуализирован.

Создание компонента React:

- `import React, { Component } from 'react'`
- Создайте класс для вашего нового компонента. Формат следующий: `class ClassNameGoesHere extends Component {}`
- Используйте метод `render() {}`, чтобы получить элементы для `render` в DOM. JSX входит в оператор `return` метода `render() {}`.
- Экспортируйте только что созданный класс либо в ту же строку его объявления, либо в конец файла.

Вот как будет выглядеть компонент `EvenAndOdd`, применив эти изменения.

```js
import React, { Component } from "react";

export default class EvenAndOdd extends Component {
  render() {
    return <p> EvenAndOdd компонент </p>;
  }
}
```

<details>

<summary> <code> FilterObject.js </code> </summary>

```js
import React, { Component } from "react";

export default class FilterObject extends Component {
  render() {
    return <p> FilterObject компонент </p>;
  }
}
```

</details>

<details>

<summary> <code> FilterString.js </code> </summary>

```js
import React, { Component } from "react";

export default class FilterString extends Component {
  render() {
    return <p> FilterString компонент </p>;
  }
}
```

</details>

<details>

<summary> <code> Palindrome.js </code> </summary>

```js
import React, { Component } from "react";

export default class Palindrome extends Component {
  render() {
    return <p> Palindrome компонент </p>;
  }
}
```

</details>

<details>

<summary> <code> Sum.js </code> </summary>

```js
import React, { Component } from "react";

export default class Sum extends Component {
  render() {
    return <p> Sum компонент </p>;
  }
}
```

</details>

<br />
После того, как вы применили те же принципы к 4 другим файлам javascript в папке «Темы», мы затем импортируем их в `TopicBrowser.js`. Точно так же, как мы импортировали `TopicBrowser` в `App.js`, мы сделаем:  
  
```js
import React, { Component } from 'react';

// Topics
import EvenAndOdd from '../Topics/EvenAndOdd'
import FilterObject from '../Topics/FilterObject'
import FilterString from '../Topics/FilterString'
import Palindrome from '../Topics/Palindrome'
import Sum from '../Topics/Sum'

export default class TopicBrowser extends Component {
  render() {
    return (
      
    )
  }
}
```  
  
Теперь, когда они импортированы в наш компонент `TopicBrowser`, мы можем отобразить их в нашем `return`. Подобно тому, как мы визуализировали `TopicBrowser` в `App.js`, мы завернем каждый импортированный компонент в `< />`. Так как мы пытаемся `render` больше, чем компонент в одну строку, нам придется обернуть компоненты в `div`. `return` метода `render` может возвращать только один элемент, но нет ограничений на то, сколько вы можете вложить в этот один элемент. Ваш `TopicBrowser` должен выглядеть сейчас так:
  
  
```js
import React, { Component } from 'react';

// Topics
import EvenAndOdd from '../Topics/EvenAndOdd'
import FilterObject from '../Topics/FilterObject'
import FilterString from '../Topics/FilterString'
import Palindrome from '../Topics/Palindrome'
import Sum from '../Topics/Sum'

export default class TopicBrowser extends Component {
  render() {
    return (
      <div>
        <EvenAndOdd />
        <FilterObject />
        <FilterString />
        <Palindrome />
        <Sum />
      </div>
    )
  }
}
```
  
</details>

### Решение
<details>

<summary> <code> TopicBrowser.js </code> </summary>

```js
import React, { Component } from 'react';

// Topics
import EvenAndOdd from '../Topics/EvenAndOdd'
import FilterObject from '../Topics/FilterObject'
import FilterString from '../Topics/FilterString'
import Palindrome from '../Topics/Palindrome'
import Sum from '../Topics/Sum'

export default class TopicBrowser extends Component {
  render() {
    return (
      <div>
        <EvenAndOdd />
        <FilterObject />
        <FilterString />
        <Palindrome />
        <Sum />
      </div>
    )
  }
}
```

</details>

<details>

<summary> <code> EvenAndOdd.js </code> </summary>

```js
import React, { Component } from 'react';

export default class EvenAndOdd extends Component {
  render() {
    return (
      <p> EvenAndOdd компонент </p>
    )
  }
}
```

</details>

<details>

<summary> <code> FilterObject.js </code> </summary>

```js
import React, { Component } from 'react';

export default class FilterObject extends Component {
  render() {
    return (
      <p> FilterObject компонент </p>
    )
  }
}
```

</details>

<details>

<summary> <code> FilterString.js </code> </summary>

```js
import React, { Component } from 'react';

export default class FilterString extends Component {
  render() {
    return (
      <p> FilterString компонент </p>
    )
  }
}
```

</details>

<details>

<summary> <code> Palindrome.js </code> </summary>

```js
import React, { Component } from 'react';

export default class Palindrome extends Component {
  render() {
    return (
      <p> Palindrome компонент </p>
    )
  }
}
```

</details>

<details>

<summary> <code> Sum.js </code> </summary>

```js
import React, { Component } from 'react';

export default class Sum extends Component {
  render() {
    return (
      <p> Sum компонент </p>
    )
  }
}
```

</details>

![3](https://user-images.githubusercontent.com/1161809/160261913-bcb4581e-c0b1-4a2d-b862-54fce28e79a5.png)
## Шаг 3

### Описание шага
В следующих шагах важно понимать, что существует более одного способа решить проблему с игрушкой; если ваше решение не совпадает с моим, ничего страшного. Кроме того, поскольку следующие 5 компонентов очень похожи по своей структуре, подробные инструкции только шага 3 подробно описаны. Другие шаги после этого не будут вдаваться в подробности.

На этом шаге мы начнем с первой темы: `EvenAndOdd`.

### Инструктаж
<b>Обзор проблемы:</b> Дана строка чисел, разделенных запятыми, разделите числа на два разных массива. Первый представляет собой массив всех четных чисел, а второй — массив всех нечетных чисел.

<b>Контур компонента:</b> один родительский элемент `div`, один элемент `h4`, один элемент `input`, один элемент `button` и два элемента `span`.

* Откройте `src/components/Topics/EvenAndOdd.js`.
* Удалите элемент `<p>` из `return` метода `render`.
* Добавьте контур компонента в `return` метода `render`.
* Добавьте в схему следующие реквизиты `className`:
  * `div` - className="puzzleBox evenAndOddPB"
  * `input` - className="inputLine"
  * `кнопка` - className="confirmationButton"
  * Оба `span`s - className="resultsBox"
* Присвоить элементу `h4` значение `"Evens and Odds"`.
* Создайте метод конструктора, который создает начальное состояние:
  * `evenArray` - по умолчанию должен быть пустым массивом.
  * `oddArray` - по умолчанию должен быть пустым массивом.
  * `userInput` - по умолчанию это должна быть пустая строка.
* Создайте свойство `onChange` для элемента `input`, которое обновляет значение `userInput` в состоянии.
* Создайте реквизит `onClick` для элемента `button`, который вызывает метод класса:
  * Этот метод должен решить проблему с игрушкой.
  * Этот метод должен обновлять значения `evenArray` и `oddArray` в состоянии.
* Назначьте один элемент `span` для отображения значения `evenArray`.
* Назначьте другой элемент `span` для отображения значения `oddArray`.

<details>

<summary> Детальные описание инструкций шага :construction: </summary>

<br />

Давайте начнем отображать на контур компонента.

```js
render() {
  <div className="puzzleBox evenAndOddPB">
    <h4> Evens and Odds </h4>
    <input className="inputLine"></input>
    <button className="confirmationButton"> Split </button>
    <span className="resultsBox"></span>
    <span className="resultsBox"></span>
  </div>
}
```
Теперь, когда у нас есть черновой набросок всего, что понадобится нашему компоненту, давайте начнем наполнять функциональность. Мы будем использовать состояние(state) для отслеживания пользовательского ввода, массива четных и массива нечетных чисел. Мы можем использовать состояние(state), определив метод `constructor() {}`. Прежде чем мы сможем использовать `state`, мы должны вызвать `super`. После вызова `super` мы можем создать наш объект состояния с помощью `this.state = {}` и добавить к нему наши три свойства.

```js
constructor() {
  super();

  this.state = {
    evenArray: [],
    oddArray: [],
    userInput: ''
  }
}
```

Затем, давайте обновим наши последние два элемента `span` чтобы отобразить наш `evenArray` и `oddArray`.

```js
render() {
  <div className="puzzleBox evenAndOddPB">
    <h4> Evens and Odds </h4>
    <input className="inputLine"></input>
    <button className="confirmationButton"> Split </button>
    <span className="resultsBox"> Evens: { JSON.stringify(this.state.evenArray) } </span>
    <span className="resultsBox"> Odds: { JSON.stringify(this.state.oddArray) } </span>
  </div>
}
```
Что такое `JSON.stringify`? Это необязательное дополнение, но без него ваш массив будет отображаться не как [1,2,3,4], а как 1234. `JSON.stringify` придает нашему отображению более читаемый формат. Вы можете просто использовать `this.state.evenArray` или `this.state.oddArray`, если хотите.

Далее давайте обновим наш элемент `input`, чтобы он обрабатывал пользовательский ввод. В React вы можете использовать атрибут `onChange`, который вызывает функцию каждый раз, когда пользователь вводит данные в поле input.

```js
render() {
  <div className="puzzleBox evenAndOddPB">
    <h4> Evens and Odds </h4>
    <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
    <button className="confirmationButton"> Split </button>
    <span className="resultsBox"> Evens: { JSON.stringify(this.state.evenArray) } </span>
    <span className="resultsBox"> Odds: { JSON.stringify(this.state.oddArray) } </span>
  </div>
}
```
Что такое "е"? `e` - это событие. В этом случае мы можем использовать событие, чтобы получить текущее значение внутри элемента `input`. Мы можем получить к нему доступ, выполнив `e.target.value`. С этой настройкой каждый раз, когда пользователь вводит в это поле `input`, вызывается наша функция стрелки, захватывая событие, а затем вызывает наш метод в классе с именем `handleChange` и передает значение, которое в данный момент находится в поле ввода. Например, если я ввел в поле `input` "1,2", то `handleChange` будет вызван три раза. Каждое нажатие клавиши вызывает `handleChange` и передает текущее значение, это будет выглядеть так:

* Первый раз: `e.target.value` = "1"
* Второй раз: `e.target.value` = "1,"
* Третий раз: `e.target.value` = "1,2"

Давайте добавим в наш класс метод с именем `handleChange` для обновления нашего свойства `state` `userInput`.
```js
handleChange(val) {
  this.setState({ userInput: val });
}
```

Теперь, когда наша функциональность ввода завершена, все, что осталось, это получить нашу кнопку для выполнения метода, который решает проблему с игрушкой. В React мы можем выполнить функцию по нажатию кнопки, используя атрибут `onClick`. Поскольку мы хотим выполнить этот метод с аргументом, мы вложим его в стрелочную функцию.

```js
render() {
  <div className="puzzleBox evenAndOddPB">
    <h4> Evens and Odds </h4>
    <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
    <button className="confirmationButton" onClick={ () => { this.assignEvenAndOdds(this.state.userInput) }}> Split </button>
    <span className="resultsBox"> Evens: { JSON.stringify(this.state.evenArray) } </span>
    <span className="resultsBox"> Odds: { JSON.stringify(this.state.oddArray) } </span>
  </div>
}
```
Теперь всякий раз, когда пользователь щелкает наш элемент `button`, вызывается наша функция стрелки, которая вызывает метод нашего класса с именем `assignEvenAndOdds` и передает текущий `userInput` в `state`. Давайте создадим этот метод в нашем классе.

```js
assignEvenAndOdds(userInput) {

}
```
Как вы решите проблему с игрушкой, зависит от вас, если вы не можете понять этот момент, тогда подсмотрите раздел решения :)
</details>

### Решение 🕵️

<details>
  <summary> <code> EvenAndOdd.js </code> </summary>

```js
import React, { Component } from 'react';

export default class EvenAndOdd extends Component {

  constructor() {
    super();

    this.state = {
      evenArray: [],
      oddArray: [],
      userInput: ''
    }
  }

  handleChange(val) {
    this.setState({ userInput: val });
  }

  assignEvenAndOdds(userInput) {
    var arr = userInput.split(',');
    var evens = [];
    var odds = [];

    for ( var i = 0; i < arr.length; i++ ) {
      if ( arr[i] % 2 === 0 ) {
        evens.push( parseInt(arr[i], 10) );
      } else {
        odds.push( parseInt(arr[i], 10) );
      }
    }
    
    this.setState({ evenArray: evens, oddArray: odds });
  }

  render() {
    return (
      <div className="puzzleBox evenAndOddPB">
        <h4> Evens and Odds </h4>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => { this.assignEvenAndOdds(this.state.userInput) }}> Split </button>
        <span className="resultsBox"> Evens: { JSON.stringify(this.state.evenArray) } </span>
        <span className="resultsBox"> Odds: { JSON.stringify(this.state.oddArray) } </span>
      </div>
    )
  }
}
```

</details>

<br /> 

![1g](https://user-images.githubusercontent.com/1161809/160263046-4cc93a3f-2548-4824-b78c-9c1de7b7cfca.gif)

## Шаг 4 

### Описание шага

В этом шаге мы создадим наш следующий `FilterObject` компонент.

### Инструкции для выполнения шага

<b>Обзор проблемы.</b> Используя заранее определенный массив объектов, отфильтруйте объекты, не имеющие заданного свойства. Отобразите новый массив, заполненный объектами, которые имеют данное свойство.

<b>Контур компонента</b>: один родительский элемент `div`, один элемент `h4`, один элемент `span`, один элемент `input`, один элемент `button` и один элемент `span`.

* Откройте `src/components/Topics/FilterObject.js`.
* Удалите элемент `<p>` из `return` метода `render`.
* Добавьте контур компонента в `return` метода `render`.
* Добавьте в схему следующие реквизиты `className`:
  * `div` - className="puzzleBox filterObjectPB"
  * Первый `span` - className="puzzleText"
  * `input` - className="inputLine"
  * `кнопка` - className="confirmationButton"
  * Последний `span` - className="resultsBox filterObjectRB"
* Присвойте элементу `h4` значение `"Filter Object"`.
* Создайте метод конструктора, который создает начальное состояние:
  * `unFilteredArray` - по умолчанию это должен быть массив объектов. Попробуйте выбрать массив объектов, которые имеют схожие свойства, но они не должны быть идентичными объектами.
  * `userInput` - по умолчанию это должна быть пустая строка.
  * `filteredArray` - по умолчанию должен быть пустым массивом.
* Создайте свойство `onChange` для элемента `input`, которое обновляет значение `userInput` в состоянии.
* Создайте реквизит `onClick` для элемента `button`, который вызывает метод класса:
  * Этот метод должен решить проблему с игрушкой.
  * Этот метод должен обновить значение `filteredArray`.
* Присвойте первому элементу `span` значение `unFilteredArray`.
* Присвойте последнему элементу `span` значение `filteredArray`.

<details>

<summary> Детальные описание инструкций шага :construction: </summary>

<br />

Итак начнем отрисовку каркаса компонента.

```js
  render() {
    return (
      <div className="puzzleBox filterObjectPB">
        <h4> Filter Object </h4>
        <span className="puzzleText"></span>
        <input className="inputLine"></input>
        <button className="confirmationButton"> Filter </button>
        <span className="resultsBox filterObjectRB"></span>
      </div>
    )
  }
```
Теперь, когда у нас есть набросок всего, что понадобится нашему компоненту, давайте начнем наполнять функциональность. Мы будем использовать состояние(state) для отслеживания пользовательского ввода, нашего нефильтрованного массива и нашего отфильтрованного массива.

```js
  constructor() {
    super();

    this.state = {
      employees: [
        {
          name: 'Jimmy Joe',
          title: 'Hack0r',
          age: 12,
        },
        {
          name: 'Jeremy Schrader',
          age: 24,
          hairColor: 'brown'
        },
        {
          name: 'Carly Armstrong',
          title: 'CEO',
        }
      ],

      userInput: '',
      filteredEmployees: []
    }
  }
```

Затем давайте обновим наши элементы `span`чтобы отобразить наши неотфильтрованный и отфильтрованный массивы employees.

```js
  render() {
    return (
      <div className="puzzleBox filterObjectPB">
        <h4> Filter Object </h4>
        <span className="puzzleText"> Original: { JSON.stringify(this.state.employees, null, 10) } </span>
        <input className="inputLine"></input>
        <button className="confirmationButton"> Filter </button>
        <span className="resultsBox filterObjectRB"> Filtered: { JSON.stringify(this.state.filteredEmployees, null, 10) } </span>
      </div>
    )
  }
```

Затем давайте обновим наш элемент `input` для обработки пользовательского ввода.

```js
  handleChange(val) {
    this.setState({ userInput: val });
  }

  render() {
    return (
      <div className="puzzleBox filterObjectPB">
        <h4> Filter Object </h4>
        <span className="puzzleText"> Original: { JSON.stringify(this.state.employees, null, 10) } </span>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton"> Filter </button>
        <span className="resultsBox filterObjectRB"> Filtered: { JSON.stringify(this.state.filteredEmployees, null, 10) } </span>
      </div>
    )
  }
```

Наконец, давайте обновим наш элемент `button` для обработки фильтрации нашего массива сотрудников.

```js
  filterEmployees(prop) {

  }

  render() {
    return (
      <div className="puzzleBox filterObjectPB">
        <h4> Filter Object </h4>
        <span className="puzzleText"> Original: { JSON.stringify(this.state.employees, null, 10) } </span>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.filterEmployees(this.state.userInput) }> Filter </button>
        <span className="resultsBox filterObjectRB"> Filtered: { JSON.stringify(this.state.filteredEmployees, null, 10) } </span>
      </div>
    )
  }
```

Как вы решите проблему с игрушкой, зависит от вас, если вы не можете понять этот момент, тогда ознакомьтесь с разделом решения.

</details>

### Решение

<details>

<summary> <code> FilterObject.js </code> </summary>

```js
import React, { Component } from 'react';

export default class FilterObject extends Component {

  constructor() {
    super();

    this.state = {
      employees: [
        {
          name: 'Jimmy Joe',
          title: 'Hack0r',
          age: 12,
        },
        {
          name: 'Jeremy Schrader',
          age: 24,
          hairColor: 'brown'
        },
        {
          name: 'Carly Armstrong',
          title: 'CEO',
        }
      ],

      userInput: '',
      filteredEmployees: []
    }
  }

  handleChange(val) {
    this.setState({ userInput: val });
  }

  filterEmployees(prop) {
    var employees = this.state.employees;
    var filteredEmployees = [];
    
    for ( var i = 0; i < employees.length; i++ ) {
      if ( employees[i].hasOwnProperty(prop) ) {
        filteredEmployees.push(employees[i]);
      }
    }

    this.setState({ filteredEmployees: filteredEmployees });
  }

  render() {
    return (
      <div className="puzzleBox filterObjectPB">
        <h4> Filter Object </h4>
        <span className="puzzleText"> Original: { JSON.stringify(this.state.employees, null, 10) } </span>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.filterEmployees(this.state.userInput) }> Filter </button>
        <span className="resultsBox filterObjectRB"> Filtered: { JSON.stringify(this.state.filteredEmployees, null, 10) } </span>
      </div>
    )
  }
}
```

</details>

<br /> 

![2g](https://user-images.githubusercontent.com/1161809/160263404-66bb4782-6c1f-448c-b087-11863446a3e0.gif)

## Шаг 5

### Описание шага 

В этом же шаге мы построим наш `FilterString` компонент.

### Инструкции для выполнения шага

<b>Обзор проблемы.</b> Используя заданный массив строк, отфильтруйте строки, не содержащие заданную строку. Отобразите новый массив, заполненный строками, которые содержат данную строку.

<b>Контур компонента:</b> один элемент `div` в скобках, один элемент `h4`, один элемент `span`, один элемент `input`, один элемент `button` и еще один элемент `span`.

* Откройте `src/components/Topics/FilterString.js`.
* Удалите элемент `<p>` из `return` метода `render`.
* Добавьте каркас компонента в `return` метода `render`.
* Добавьте в схему следующие реквизиты `className`:
  * `div` - className="puzzleBox filterStringPB"
  * Первый `span` - className="puzzleText"
  * `input` - className="inputLine"
  * `кнопка` - className="confirmationButton"
  * Последний `span` - className="resultsBox filterStringRB"
* Присвойте элементу `h4` значение `"Filter String`.
* Создайте метод конструктора, который создает начальное состояние:
  * `unFilteredArray` - по умолчанию это должен быть массив строк. Вы выбираете, какие строки пойдут в массив.
  * `userInput` - по умолчанию это должна быть пустая строка.
  * `filteredArray` - по умолчанию должен быть пустым массивом.
* Создайте свойство `onChange` для элемента `input`, которое обновляет значение `userInput` в состоянии.
* Создайте реквизит `onClick` для элемента `button`, который вызывает метод класса:
  * Этот метод должен решить проблему с игрушкой.
  * Этот метод должен обновить значение `filteredArray`.
* Присвойте первому элементу `span` значение `unFilteredArray`.
* Присвойте последнему элементу `span` значение `filteredArray`.

<details>

<summary> Детальные описание инструкций шага :construction: </summary>

<br />

Давайте начнем рендеринг каркаса нашего компонента.

```js
  render() {
    return (
      <div className="puzzleBox filterStringPB">
        <h4> Filter String </h4>
        <span className="puzzleText"></span>
        <input className="inputLine"></input>
        <button className="confirmationButton"> Filter </button>
        <span className="resultsBox filterStringRB"></span>
      </div>
    )
  }
```
Теперь, когда у нас есть набросок всего, что понадобится нашему компоненту, давайте начнем наполнять функциональность. Мы будем использовать состояние для отслеживания пользовательского ввода, нашего нефильтрованного массива и нашего отфильтрованного массива.

```js
  constructor() {
    super();

    this.state = {
      names: ['James', 'Jessica', 'Melody', 'Tyler', 'Blake', 'Jennifer', 'Mark', 'Maddy'],
      userInput: '',
      filteredNames: []
    };
  }
```
Далее давайте обновим наши элементы `span`, чтобы отобразить наш нефильтрованный и отфильтрованный массив имен.

```js
  render() {
    return (
      <div className="puzzleBox filterStringPB">
        <h4> Filter String </h4>
        <span className="puzzleText"> Names: { JSON.stringify(this.state.names, null, 10) } </span>
        <input className="inputLine"></input>
        <button className="confirmationButton"> Filter </button>
        <span className="resultsBox filterStringRB"> Filtered Names: { JSON.stringify(this.state.filteredNames, null, 10) } </span>
      </div>
    )
  }
```
Далее давайте обновим наш элемент `input`, чтобы он обрабатывал пользовательский ввод.

```js
  handleChange(val) {
    this.setState({ userInput: val });
  }

  render() {
    return (
      <div className="puzzleBox filterStringPB">
        <h4> Filter String </h4>
        <span className="puzzleText"> Names: { JSON.stringify(this.state.names, null, 10) } </span>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton"> Filter </button>
        <span className="resultsBox filterStringRB"> Filtered Names: { JSON.stringify(this.state.filteredNames, null, 10) } </span>
      </div>
    )
  }
```
Наконец, давайте обновим наш элемент `button`, чтобы обрабатывать фильтрацию нашего массива имен.

```js
  filterNames(userInput) {

  }

  render() {
    return (
      <div className="puzzleBox filterStringPB">
        <h4> Filter String </h4>
        <span className="puzzleText"> Names: { JSON.stringify(this.state.names, null, 10) } </span>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.filterNames(this.state.userInput) }> Filter </button>
        <span className="resultsBox filterStringRB"> Filtered Names: { JSON.stringify(this.state.filteredNames, null, 10) } </span>
      </div>
    )
  }
```
Как вы решите проблему с игрушкой, зависит от вас, если вы не можете понять этот момент, ознакомьтесь с разделом решения.

</details>

### Решение

<details>

<summary> <code> FilterString.js </code> </summary>

```js
import React, { Component } from 'react';

export default class FilterString extends Component {

  constructor() {
    super();

    this.state = {
      names: ['James', 'Jessica', 'Melody', 'Tyler', 'Blake', 'Jennifer', 'Mark', 'Maddy'],
      userInput: '',
      filteredNames: []
    };
  }

  handleChange(val) {
    this.setState({ userInput: val });
  }

  filterNames(userInput) {
    var names = this.state.names;
    var filteredNames = [];

    for ( var i = 0; i < names.length; i++ ) {
      if ( names[i].includes(userInput) ) {
        filteredNames.push(names[i]);
      }
    }

    this.setState({ filteredNames: filteredNames });
  }

  render() {
    return (
      <div className="puzzleBox filterStringPB">
        <h4> Filter String </h4>
        <span className="puzzleText"> Names: { JSON.stringify(this.state.names, null, 10) } </span>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.filterNames(this.state.userInput) }> Filter </button>
        <span className="resultsBox filterStringRB"> Filtered Names: { JSON.stringify(this.state.filteredNames, null, 10) } </span>
      </div>
    )
  }
}
```

</details>

<br />

![3g](https://user-images.githubusercontent.com/1161809/160263739-357876d8-020f-41f8-be51-96977a6e7418.gif)

## Шаг 6

### Описание шага

В этом шаге мы создадим наш `Palindrome` компонент.

### Инструкции для выполнения шага

<b>Обзор проблемы:</b> Используя заданную строку, определите, пишется ли она так же, как в обратном направлении, так и в прямом.

<b>Каркас компонента:</b> один родительский элемент `div`, один элемент `h4`, один элемент `input`, один элемент `button` и один элемент `span`.

* Откройте `src/components/Topics/Palindrome.js`.
* Удалите элемент `<p>` из `return` метода `render`.
* Добавьте контур компонента в `return` метода `render`.
* Добавьте в схему следующие реквизиты `className`:
  * `div` - className="puzzleBox filterStringPB"
  * `input` - className="inputLine"
  * `кнопка` - className="confirmationButton"
  * `промежуток` - className="resultsBox"
* Присвойте элементу `h4` значение `"Palindrome"`.
* Создайте метод конструктора, который создает начальное состояние:
  * `userInput` - по умолчанию это должна быть пустая строка.
  * `palindrome` - по умолчанию это должна быть пустая строка.
* Создайте свойство `onChange` для элемента ввода, которое обновляет значение `userInput` в состоянии.
* Создайте реквизит `onClick` для элемента `button`, который вызывает метод класса:
  * Этот метод должен решить проблему с игрушкой.
  * Этот метод должен обновить значение `palindrome`.
* Присвойте элементу `span` значение `palindrome`.

<details>

<summary> Детальные описание инструкций шага :construction: </summary>

<br />

Начнем отрисовку каркаса нашего компонента.

```js
  render() {
    return (
      <div className="puzzleBox palindromePB">
        <h4> Palindrome </h4>
        <input className="inputLine"></input>
        <button className="confirmationButton"> Check </button>
        <span className="resultsBox"></span>
      </div>
    )
  }
```
Теперь, когда у нас есть набросок всего, что понадобится нашему компоненту, давайте начнем наполнять функциональность. Мы будем использовать состояние, чтобы отслеживать, что вводит пользователь, и является ли пользовательский ввод палиндромом или нет.

```js
  constructor() {
    super();

    this.state = {
      userInput: '',
      palindrome: ''
    };
  }
```

Затем, обновим наш элемент `span` чтобы он отображал `palindrome`.

```js
  render() {
    return (
      <div className="puzzleBox palindromePB">
        <h4> Palindrome </h4>
        <input className="inputLine"></input>
        <button className="confirmationButton"> Check </button>
        <span className="resultsBox"> Palindrome: { this.state.palindrome } </span>
      </div>
    )
  }
```

Затем обновим наш элемент `input` чтобы отследить пользовательский ввод.

```js
  handleChange(val) {
    this.setState({ userInput: val });
  }

  render() {
    return (
      <div className="puzzleBox palindromePB">
        <h4> Palindrome </h4>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton"> Check </button>
        <span className="resultsBox"> Palindrome: { this.state.palindrome } </span>
      </div>
    )
  }
```

Наконец, давайте обновим наш элемент `button` для обработки установки значения `palindrome` на `"true"` или `"false"`.

```js
  isPalindrome(userInput) {

  }

  render() {
    return (
      <div className="puzzleBox palindromePB">
        <h4> Palindrome </h4>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.isPalindrome(this.state.userInput) }> Check </button>
        <span className="resultsBox"> Palindrome: { this.state.palindrome } </span>
      </div>
    )
  }
```

Как вы решите проблему с игрушкой, зависит от вас, если вы не можете понять этот момент, ознакомьтесь с разделом решения. 

</details>

### Решение

<details>

<summary> <code> Palindrome.js </code> </summary>

```js
import React, { Component } from 'react';

export default class Palindrome extends Component {

  constructor() {
    super();

    this.state = {
      userInput: '',
      palindrome: ''
    };
  }

  handleChange(val) {
    this.setState({ userInput: val });
  }

  isPalindrome(userInput) {
    var forwards = userInput;
    var backwards = userInput;
    backwards = backwards.split('');
    backwards = backwards.reverse();
    backwards = backwards.join('');

    if ( forwards === backwards ) {
      this.setState({ palindrome: 'true' });
    } else {
      this.setState({ palindrome: 'false' });
    }
  }

  render() {
    return (
      <div className="puzzleBox palindromePB">
        <h4> Palindrome </h4>
        <input className="inputLine" onChange={ (e) => this.handleChange(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.isPalindrome(this.state.userInput) }> Check </button>
        <span className="resultsBox"> Palindrome: { this.state.palindrome } </span>
      </div>
    )
  }
}
```

</details>

<br />

![4g](https://user-images.githubusercontent.com/1161809/160263997-4f1501d6-618f-43e4-a6d8-f8250e56aa92.gif)

## Шаг 7

### Описание шага

В этом, заключительном шаге мы построим наш `Sum` компонент.

### Инструкции для выполнения шага

<b>Сводка проблемы:</b> Учитывая два числа, подсчитайте сумму и отобразите ее.

<b>Контур компонента:</b> один родительский элемент `div`, один элемент `h4`, два элемента `input`, один элемент `button` и один элемент `span`.

* Откройте src/components/Topics/Sum.js.
* Удалите элемент `<p>` из `return` метода `render`.
* Добавьте контур компонента в `return` метода `render`.
* Добавьте в схему следующие реквизиты `className`:
  * `div` - className="puzzleBox sumPB"
  * Два `input` - className="inputLine"
  * `кнопка` - className="confirmationButton"
  * `промежуток` - className="resultsBox"
* Присвойте элементу `h4` значение `"Sum"`.
* Создайте метод конструктора, который создает начальное состояние:
  * `number1` — по умолчанию должно быть `0`.
  * `number2` — по умолчанию должно быть `0`.
  * `sum` - по умолчанию должно быть `null`.
* Создайте реквизит `onChange` для первого элемента `input`, который обновляет значение `number1` в состоянии.
* Создайте реквизит `onChange` для второго элемента `input`, который обновляет значение `number2` в состоянии.
* Создайте свойство `onClick` для элемента кнопки, которое вызывает метод класса:
  * Этот метод должен решить проблему с игрушкой.
  * Этот метод должен обновлять значение `sum`.
* Присвоить элементу `span` значение `sum`.

<details>

<summary> Детальные описание инструкций шага :construction: </summary>

<br />

Давайте начнем рендеринг каркаса нашего компонента.

```js
  render() {
    return (
      <div className="puzzleBox sumPB">
        <h4> Sum </h4>
        <input className="inputLine" type="number"></input>
        <input className="inputLine" type="number"></input>
        <button className="confirmationButton"> Add </button>
        <span className="resultsBox"></span>
      </div>
    )
  }
```

Теперь, когда у нас есть набросок всего, что понадобится нашему компоненту, давайте начнем наполнять функциональность. Мы будем использовать состояние для отслеживания двух чисел, которые дает нам пользователь, и суммы этих двух чисел.

```js
  constructor() {
    super();

    this.state = {
      number1: 0,
      number2: 0,
      sum: null
    }
  }
```
Затем давайте обновим наш элемент `span` чтобы он отображал `sum`.

```js
  render() {
    return (
      <div className="puzzleBox sumPB">
        <h4> Sum </h4>
        <input className="inputLine" type="number"></input>
        <input className="inputLine" type="number"></input>
        <button className="confirmationButton"> Add </button>
        <span className="resultsBox"> Sum: {this.state.sum} </span>
      </div>
    )
  }
```

Затем обновим наши элементы `input` для перехвата пользовательского ввода.

```js
  updateNumber1(val) {
    this.setState({ number1: parseInt(val, 10) });
  }

  updateNumber2(val) {
    this.setState({ number2: parseInt(val, 10) });
  }

  render() {
    return (
      <div className="puzzleBox sumPB">
        <h4> Sum </h4>
        <input className="inputLine" type="number" onChange={ (e) => this.updateNumber1(e.target.value) }></input>
        <input className="inputLine" type="number" onChange={ (e) => this.updateNumber2(e.target.value) }></input>
        <button className="confirmationButton"> Add </button>
        <span className="resultsBox"> Sum: {this.state.sum} </span>
      </div>
    )
  }
```

Наконец, давайте обновим нащ элемент `button` для обновления значения `sum`.

```js
  add(num1, num2) {

  }

  render() {
    return (
      <div className="puzzleBox sumPB">
        <h4> Sum </h4>
        <input className="inputLine" type="number" onChange={ (e) => this.updateNumber1(e.target.value) }></input>
        <input className="inputLine" type="number" onChange={ (e) => this.updateNumber2(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.add(this.state.number1, this.state.number2) }> Add </button>
        <span className="resultsBox"> Sum: {this.state.sum} </span>
      </div>
    )
  }
```

Как вы решите проблему с игрушкой, зависит от вас, если вы не можете понять этот момент, ознакомьтесь с разделом решения.

</details>

### Solution

<details>

<summary> <code> Sum.js </code> </summary>

```js
import React, { Component } from 'react';

export default class Sum extends Component {

  constructor() {
    super();

    this.state = {
      number1: 0,
      number2: 0,
      sum: null
    }
  }

  updateNumber1(val) {
    this.setState({ number1: parseInt(val, 10) });
  }

  updateNumber2(val) {
    this.setState({ number2: parseInt(val, 10) });
  }

  add(num1, num2) {
    this.setState({ sum: num1 + num2 });
  }

  render() {
    return (
      <div className="puzzleBox sumPB">
        <h4> Sum </h4>
        <input className="inputLine" type="number" onChange={ (e) => this.updateNumber1(e.target.value) }></input>
        <input className="inputLine" type="number" onChange={ (e) => this.updateNumber2(e.target.value) }></input>
        <button className="confirmationButton" onClick={ () => this.add(this.state.number1, this.state.number2) }> Add </button>
        <span className="resultsBox"> Sum: {this.state.sum} </span>
      </div>
    )
  }
}
```

</details>

<br />

![5g](https://user-images.githubusercontent.com/1161809/160264218-130dcf40-bbb2-4a0e-b271-45d96ccf5813.gif)

## На этом почти все

Чтобы продвинуть этот проект на шаг вперед, попробуйте добавить в проект больше игрушечных задач за время, в один месяц. Это совершенно необязательно, однако этот проект может стать «демонстрацией» ваших знаний для решения задач.

## Contribs

Если вы обнаружите проблему или опечатку, сделайте форк, внесите необходимые изменения и создайте запрос на вытягивание, чтобы я мог просмотреть ваши изменения и объединить их с основным репозиторием и веткой.

