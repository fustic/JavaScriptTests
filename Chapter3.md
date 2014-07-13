## Глава 3. Типы, структуры данных
### Тема 1. Числа, округления
1. Чему будет равно выражение
  ```javascript
  var result = -1 / 0;
  ```
  ```javascript
  1. -Infinity
  ```
  ```javascript
  2. Infinity
  ```
  ```javascript
  3. Number.NEGATIVE_INFINITY
  ```
  ```javascript
  4. -Number.POSITIVE_INFINITY
  ```
  ```javascript
  5. NaN
  ```

  *Правильные ответы:* **1, 3, 4**

2. В резуьтате каких операций можно получить `NaN`
  ```javascript
  1. -1 / -Infinity
  ```
  ```javascript
  2. -1 / 0
  ```
  ```javascript
  3. 0 / 0
  ```
  ```javascript
  4. Number.POSITIVE_INFINITY / -Number.POSITIVE_INFINITY
  ```
  ```javascript
  5. Infinity * Number.POSITIVE_INFINITY
  ```

  *Правильные ответы:* **3, 4**

3. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. 1 / 0 === Infinity
  ```
  ```javascript
  2. -1 / 0 === -Number.POSITIVE_INFINITY
  ```
  ```javascript
  3. -0.5 + 0.6 === 0.1
  ```
  ```javascript
  4. Number.MAX_VALUE + Math.pow(2, 12) === Number.MAX_VALUE
  ```
  ```javascript
  5. Number.POSITIVE_INFINITY === Number.MAX_VALUE + Infinity
  ```

  *Правильные ответы:* **1, 2, 4, 5**

4. Какие из нижеперечисленных выражений ложны
  ```javascript
  1. 9999999999999999 < 10000000000000000
  ```
  ```javascript
  2. NaN === NaN
  ```
  ```javascript
  3. Number.MAX_VALUE + Math.pow(2, 10) === Number.MAX_VALUE
  ```
  ```javascript
  4. -0.9 + 1.4 === 0.5
  ```
  ```javascript
  5. 0 === 0
  ```

  *Правильные ответы:* **1, 2, 4 **

5. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. Math.ceil(Math.pow(2, 4)) === Math.floor(Math.pow(2, 4))
  ```
  ```javascript
  2. Number.POSITIVE_INFINITY === Infinity
  ```
  ```javascript
  3. -0.9 + 1.4 === 0.5
  ```
  ```javascript
  4. isNaN(0) === false
  ```
  ```javascript
  5. isNaN(0) === true
  ```

  *Правильные ответы:* **1, 2, 4**

### Тема 2.Приведение типов
1. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. new Number(10) === 10
  ```
  ```javascript
  2. (2).toString() === 2..toString()
  ```
  ```javascript
  3. !!'1'
  ```
  ```javascript
  4. 0 === 0
  ```
  ```javascript
  5. false == 'false'
  ```

  *Правильные ответы:* **2, 3, 4**


2. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. new Number(10) + 0 === 10;
  ```
  ```javascript
  2. 2..toString() === 2..toString()
  ```
  ```javascript
  3. !!''
  ```
  ```javascript
  4. 0 == '0'
  ```
  ```javascript
  5. 'true' == true
  ```

  *Правильные ответы:* **1, 2, 4, **

3. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. Number(10) === 10
  ```
  ```javascript
  2. 2..toFixed(1) === 2.0.toString()
  ```
  ```javascript
  3. !!{}
  ```
  ```javascript
  4. '0' == 0
  ```
  ```javascript
  5. true === true
  ```

  *Правильные ответы:* **1, 3, 4, 5 **

4. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. +'10' === 10
  ```
  ```javascript
  2. new String(2).toString() == 2
  ```
  ```javascript
  3. !!0
  ```
  ```javascript
  4. 0 == 0
  ```
  ```javascript
  5. null == undefined
  ```

  *Правильные ответы:* **1, 2, 4, 5**

5. Какие из нижеперечисленных выражений истинны
  ```javascript
  1. !!!{}
  ```
  ```javascript
  2. +'2.0' == (2).toString()
  ```
  ```javascript
  3. !!'mail.ru'
  ```
  ```javascript
  4. +0 === +'0'
  ```
  ```javascript
  5. null === undefined
  ```

  *Правильные ответы:* **2, 3, 4**

### Тема 3. Работа со строками
1. Какие из нижеперечисленных выражений истинны
  ```javascript
  var myString = 'mail.ru';
  ```

  ```javascript
  1. myString.charAt(0) === 'm'
  ```
  ```javascript
  2. myString.substring(1, 4) === 'mail'
  ```
  ```javascript
  3. myString.slice(-myString.indexOf('.')) === 'l.ru'
  ```
  ```javascript
  4. myString.split('.')[0] === 'mail'
  ```
  ```javascript
  5. myString.slice(1, -1) === 'ail'
  ```

  *Правильные ответы:* **1, 3, 4 **

2. Какие из нижеперечисленных выражений истинны
  ```javascript
  var myString = 'mail.ru';
  ```

  ```javascript
  1. myString.charAt(myString.length) === 'u'
  ```
  ```javascript
  2. myString.substring(1, 4) === 'ail'
  ```
  ```javascript
  3. myString.slice(-4) === 'l.ru'
  ```
  ```javascript
  4. myString.split('.')[0] === 'mail.'
  ```
  ```javascript
  5. myString.slice(1, -1) === 'ail.r'
  ```

  *Правильные ответы:* **2, 3, 5**

3. Какие из нижеперечисленных выражений истинны
  ```javascript
  var myString = 'mail.ru';
  ```

  ```javascript
  1. myString.charAt(myString.length - 1) === 'u'
  ```
  ```javascript
  2. myString.substr(1, 4) === 'ail'
  ```
  ```javascript
  3. myString.slice(0) === myString
  ```
  ```javascript
  4. myString.split('.')[1] === 'ru'
  ```
  ```javascript
  5. myString.slice(1, -3) === 'ail.r'
  ```

  *Правильные ответы:* **1, 3, 4**

4. Какие из нижеперечисленных выражений истинны
  ```javascript
  var myString = 'mail.ru';
  ```

  ```javascript
  1. myString.charAt(myString.indexOf('.')) === '.'
  ```
  ```javascript
  2. myString.substr(1, 4) === 'ail.'
  ```
  ```javascript
  3. myString.slice(-1) === 'r'
  ```
  ```javascript
  4. myString.split('.')[1] === '.ru'
  ```
  ```javascript
  5. myString.slice(0, 0) === ''
  ```

  *Правильные ответы:* **1, 2, 5**

5. Какие из нижеперечисленных выражений истинны
  ```javascript
  var myString = 'mail.ru';
  ```

  ```javascript
  1. myString.charAt(myString.lastIndexOf('.')) === '.'
  ```
  ```javascript
  2. myString.substr(myString.lastIndexOf('.')) === '.ru'
  ```
  ```javascript
  3. myString.slice(-1) === 'm'
  ```
  ```javascript
  4. myString.split()[0] === myString
  ```
  ```javascript
  5. myString.slice(0, 0) === 'm'
  ```

  *Правильные ответы:* **1, 2, 4**

### Тема 4. Создание массива
1. Какой код создаст массив с длинной 10

  ```javascript
  1. var array = new Array(10)
  ```
  ```javascript
  2. var array = new Array('10')
  ```
  ```javascript
  3. var array = [10]
  ```
  ```javascript
  4. var array = [Math.pow(10, 9)].join().split('')
  ```
  ```javascript
  5. var array = 10 * [10]
  ```

  *Правильные ответы:* **1, 4**

2. Какой код создаст массив с длинной 100

  ```javascript
  1. var array = new Array(100)
  ```
  ```javascript
  2. var array = new Array('100')
  ```
  ```javascript
  3. var array = [100]
  ```
  ```javascript
  4. var array = [Math.pow(100, 10)].join().split('')
  ```
  ```javascript
  5. var array = 10 * [100]
  ```

  *Правильные ответы:* **1, **

3. Какой код создаст массив с длинной 1

  ```javascript
  1. var array = new Array(1)
  ```
  ```javascript
  2. var array = new Array('1')
  ```
  ```javascript
  3. var array = [1]
  ```
  ```javascript
  4. var array = [,]
  ```
  ```javascript
  5. var array = 1 * [1]
  ```

  *Правильные ответы:* **1, 2, 3, 4 **

4. Какой код создаст массив с длинной 5

  ```javascript
  1. var array = new Array(5)
  ```
  ```javascript
  2. var array = new Array('5')
  ```
  ```javascript
  3. var array = [5]
  ```
  ```javascript
  4. var array = [,1,,,5]
  ```
  ```javascript
  5. var array = 5 * [5]
  ```

  *Правильные ответы:* **1, 4**

5. Какой код создаст массив с длинной 0

  ```javascript
  1. var array = new Array(0)
  ```
  ```javascript
  2. var array = new Array('0')
  ```
  ```javascript
  3. var array = [0]
  ```
  ```javascript
  4. var array = [,]
  ```
  ```javascript
  5. var array = []
  ```

  *Правильные ответы:* **1, 5**

### Тема 5. Работа с массивами
1.
