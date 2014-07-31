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
      
### Тема 4. Объект RegExp
1. Какие выражения истинны
  ```javascript
  var
    re = new RegExp('\\d+', 'gi'),
    str = 'MailRu Group 1998 - 2014';
  ```
  1. `re.global`
  2. `re.exec(str)[0] === ['1998'][0]`
  3. `re.exec(str);
      re.exec(str)[0] === ['1998'][0]`
  4. `re.test(str)`
  5. `re.lastIndex === undefined`
  
  *Правильные ответы:* **1, 2, 4**
  
2. Какие выражения истинны
  ```javascript
  var
    re = new RegExp('^[a-z]{5}', 'mi'),
    str = 'MailRu Group 1998 - 2014';
  ```
  1. `re.multiline`
  2. `re.exec(str)[0] === ['MailR'][0]`
  3. `re.exec(str);
      re.exec(str)[0] === ['MailR'][0]`
  4. `re.test(str)`
  5. `re.lastIndex === undefined`
  
  *Правильные ответы:* **1, 2, 3, 4**
  
3. Какие выражения истинны
  ```javascript
  var
    re = new RegExp('(\\W*\\s|\\D\\s){2}', 'i'),
    str = 'MailRu Group 1998 - 2014'; 
  ```
  1. `re.ignoreCase`
  2. `re.test(str) === re.test()` 
  3. `re.exec(str)[0] === [" - ", "- "][0]`
  4. `re.test(str)
      re.exec(str)[0] === [" - ", "- "][1]`
  5. `re.exec(str)[0] === [" - ", "- "][1]`
  
  *Правильные ответы:* **1, 3**
  
4. Какие выражения истинны
  ```javascript
  var
    re = new RegExp('\\d*$', 'i'),
    str = 'MailRu Group 1998 - 2014';
  ```
  1. `re.multiline`
  2. `re.test(str) === re.test()`
  3. `re.exec(str)[0] === ["2014"][0]`
  4. `re.test(str)
      re.exec(str)[0] === ["2014"][0]`
  5. `!!re.lastIndex`
  
  *Правильные ответы:* **2, 3, 4**
  
5. Какие выражения истинны
  ```javascript
  var 
    re = new RegExp('.*'),
    str = 'MailRu Group 1998 - 2014';
  ```
  1. `re.global`
  2. `re.test(str)`
  3. `re.exec(str)[0] === str`
  4. `re.exec(str) === str`
  5. `re.test(str);
      re.exec(str) === str`
  
  *Правильные ответы:* **2, 3**
  
### Тема 5. Методы класса String
1. Какие выражения истинны
  ```javascript
  var
    re = /((https?:\/\/(www\.)?|www\.)\S+$)/i,
    str = 'MailRu Group 1998 - 2014 http://corp.mail.ru/++';
  ```
  1. `str.match(re)[0] === 'http://corp.mail.ru/++'`
  2. `str.replace('+', '').match(re)[0] === 'http://corp.mail.ru/'`
  3. `str.replace(/\+/gi, '').match(re)[0] === 'http://corp.mail.ru/'`
  4. `str.search(re) === str.indexOf('http')`
  5. `str.split(re)[1] === str.match(re)[0]`
  
  *Правильные ответы:* **1, 3, 4, 5**

2. Какие выражения истинны
  ```javascript
  var
    re = /((https?:\/\/(www\.)?|www\.)\S+$)/i,
    str = 'MailRu Group 1998 - 2014 https://corp.mail.ru/**';
  ```
  1. `str.match(re)[0] === 'https://corp.mail.ru/**'`
  2. `str.replace('*', '').match(re)[0] === 'https://corp.mail.ru/'`
  3. `str.replace(/\*/gi, '').match(re)[0] === 'https://corp.mail.ru/'`
  4. `str.search(re) === str.indexOf('https')`
  5. `str.split(re)[1] === str.match(re)[0]`
  
  *Правильные ответы:* **1, 3, 4, 5**
  
3. Какие выражения истинны
  ```javascript
  var
    re = /((https?:\/\/(www\.)?|www\.)\S+$)/i,
    str = 'MailRu Group 1998 - 2014 http://www.corp.mail.ru/--';
  ```
  1. `str.match(re)[0] === 'http://www.corp.mail.ru/--'`
  2. `str.replace('-', '').match(re)[0] === 'http://www.corp.mail.ru/'`
  3. `str.replace(/\-/gi, '').match(re)[0] === 'http://corp.mail.ru/'`
  4. `str.search(re) === str.indexOf('http')`
  5. `str.split(re)[1] === str.match(re)[0]`
  
  *Правильные ответы:* **1, 4, 5**
  
4. Какие выражения истинны
  ```javascript
  var
    re = /((https?:\/\/(www\.)?|www\.)\S+$)/i,
    str = 'MailRu Group 1998 - 2014 https://www.corp.mail.ru/!!';
  ```
  1. `str.match(re)[0] === 'https://www.corp.mail.ru/!!'`
  2. `str.replace('!', '').match(re)[0] === 'https://www.corp.mail.ru/'`
  3. `str.replace(/\!/gi, '').match(re)[0] === 'https://www.corp.mail.ru/'`
  4. `str.search(re) === str.indexOf('http')`
  5. `str.split(re)[1] === str.match(re)[0]`
  
  *Правильные ответы:* **1, 3, 4, 5**
  
5. Какие выражения истинны
  ```javascript
  var
    re = /(((https?|ftp):\/\/(www\.)?|www\.)\S+$)/i,
    str = 'MailRu Group 1998 - 2014 ftp://corp.mail.ru/++';
  ```
  1. `str.match(re)[0] === 'ftp://corp.mail.ru/++'`
  2. `str.replace('+', '').match(re)[0] === 'ftp://corp.mail.ru/'`
  3. `str.replace(/\+/gi, '').match(re)[0] === 'ftp://corp.mail.ru/'`
  4. `str.search(re) === str.indexOf('ftp')`
  5. `str.split(re)[1] === str.match(re)[0]`
    
  *Правильные ответы:* **1, 3, 4, 5**
          