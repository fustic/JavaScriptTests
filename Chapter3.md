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
1. 