## Глава 8. Регулярные выражения
### Тема 1. Флаги
1. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/m/)
  ```
  1. 'm'
  2. 'M'
  3. ['m']
  4. ['M']
  5. ['M', 'm'] 
  
  *Правильные ответы:* **3**

2. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/m/i)
  ```
  1. 'm'
  2. 'M'
  3. ['m']
  4. ['M']
  5. ['M', 'm'] 
  
  *Правильные ответы:* **4**

3. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/m/g)
  ```
  1. 'm'
  2. 'M'
  3. ['m']
  4. ['M']
  5. ['M', 'm'] 
  
  *Правильные ответы:* **3**

4. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/m/gi)
  ```
  1. 'm'
  2. 'M'
  3. ['m']
  4. ['M']
  5. ['M', 'm'] 
  
  *Правильные ответы:* **5**

5. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/M/gim)
  ```
  1. 'm'
  2. 'M'
  3. ['m']
  4. ['M']
  5. ['M', 'm'] 
  
  *Правильные ответы:* **5**

### Тема 2. Группировка
1. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/(ma)+(il)/)
  ```
  1. ['mail', 'ma', 'il']
  2. 'mail'
  3. ['Ma', 'il', 'ma', 'il']
  4. 'Mailmail'
  5. ['Mail', 'mail'] 
  
  *Правильные ответы:* **1**

2. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/(ma)+(il)/gi)
  ```
  1. ['mail', 'ma', 'il']
  2. 'mail'
  3. ['Ma', 'il', 'ma', 'il']
  4. 'Mailmail'
  5. ['Mail', 'mail'] 
  
  *Правильные ответы:* **5**

3. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/[a-z]*(il)/)
  ```
  1. ['ail', 'a', 'il']
  2. 'ail'
  3. ['Ma', 'il', 'ma', 'il']
  4. 'Mailmail'
  5. ['ail', 'il'] 
  
  *Правильные ответы:* **5**

4. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/[a-z]+[a-z]?/i)
  ```
  1. ['ail', 'u', 'roup', 'mailru', 'group']
  2. ['MailRu', 'Group', 'mailru', 'group']
  3. ['MailRu', '']
  4. 'Mailmail'
  5. ['MailRu']
  
  *Правильные ответы:* **5**


5. Что будет в результате выполнения регулярного выражения
  ```javascript
  'MailRu Group mailru group'.match(/[a-z]+(ru)/ig)
  ```
  1. ['mailru']
  2. ['MailRu', 'Ru']
  3. ['MailRu', 'mailru']
  4. 'Mailrumailru'
  5. ['MailRu']
  
  *Правильные ответы:* **3**
  
### Тема 3. Ссылки, символьные классы
1. Какие выражения истинны
  ```javascript
  var str = 'MailRu Group 1998 - 2014';
  ```
  1. `str.search(/\d - \d/) === 16`
  2. `str.search(/\W+/gi) === 18`
  3. `str.search(/(\w|\d)\s+/i) === 5`
  4. `str.search(/(\w+5|\d)\D+/i) === 13`
  5. `str.search(/\s+[.|\W]\D+/i) === 17`
  
  *Правильные ответы:* **1, 3, 5**
  
2. Какие выражения истинны
  ```javascript
  var str = 'MailRu Group 1998 - 2014';
  ```
  1. `str.search(/\d-\d/) === 16`
  2. `str.search(/\W+/gi) === 6`
  3. `str.search(/(\w|\d)\s+/i) === 16`
  4. `str.search(/(\w+1|\d+)\D+/i) === 13`
  5. `str.search(/\s+[.+|\W]\D+/i) === 17`
  
  *Правильные ответы:* **2, 4, 5**
    
3. Какие выражения истинны
  ```javascript
  var str = 'MailRu Group 1998 - 2014';
  ```
  1. `str.search(/\d\s+-\s+\d/) === 16`
  2. `str.search(/\W\D/gi) === -1`
  3. `str.search(/(\w|\d)\s?/i) === 0`
  4. `str.search(/(\w+2|\d+2)\D+/i) === -1`
  5. `str.search(/\s+[.+|\W]\D+/i) === 8`
  
  *Правильные ответы:* **1, 3, 4**

4. Какие выражения истинны
  ```javascript
  var str = 'MailRu Group 1998 - 2014';
  ```
  1. `str.search(/\d\s?-\s?\d/) === 16`
  2. `str.search(/\W+2/gi) === 17`
  3. `str.search(/(\W|\D)\s?/i) === 0`
  4. `str.search(/(\w+2|\d+2)\D+/i) === 13`
  5. `str.search(/\s+[.+|\W]\D+/i) === 17`
  
  *Правильные ответы:* **1, 2, 3, 5**
  
5. Какие выражения истинны
  ```javascript
  var str = 'MailRu Group 1998 - 2014';
  ```
  1. `str.search(/\d\s*-\s*\d/) === 16`
  2. `str.search(/\W?2/gi) === -1`
  3. `str.search(/(\W|\D)\s+/i) === 5`
  4. `str.search(/(\w+5|\d)\D+/i) === 16`
  5. `str.search(/\s+[.+|\W]\D+/i) === -1`
  
  *Правильные ответы:* **1, 3, 4**
      