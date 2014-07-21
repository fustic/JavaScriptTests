## Глава 5. Классы, модули, прототипы
### Тема 1. instanceOf
1. Какие из ниже перечисленных выражений истинны.
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
    },
    MailRu = function () {
      this.name = 'MailRu';
    };
  MailRuGroup.prototype.numberOfUsers = 100; 
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  
  var
    mailRu = new MailRu(),
    mailRuGroup = new MailRuGroup();
  
  ```
  
  ```javascript
  1. mailRuGroup.numberOfUsers === mailRu.numberOfUsers
  ```
  ```javascript
  2. mailRu.numberOfUsers === undefined
  ```
  ```javascript
  3. mailRu instanceof MailRuGroup
  ```  
  ```javascript
  4. mailRu instanceof MailRu
  ```
  ```javascript
  5. mailRuGroup.name === mailRu.name
  ```    
  
  *Правильные ответы:* **1, 3, 4**  
  
2. Какие из ниже перечисленных выражений истинны.
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
    },
    MailRu = function () {
      this.name = 'MailRu';
    };
  MailRuGroup.prototype.numberOfUsers = 100; 
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  
  var
    mailRu = new MailRu(),
    mailRuGroup = new MailRuGroup();
  
  ```
  
  ```javascript
  1. mailRu.numberOfUsers === mailRu.prototype.numberOfUsers
  ```
  ```javascript
  2. mailRu.numberOfUsers === 100
  ```
  ```javascript
  3. mailRu instanceof MailRuGroup
  ```  
  ```javascript
  4. mailRuGroup instanceof MailRu
  ```
  ```javascript
  5. mailRu.name === 'MailRuGroup'
  ```    
  
  *Правильные ответы:* **2, 3**  

3. Какие из ниже перечисленных выражений истинны.
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
    },
    MailRu = function () {
      this.name = 'MailRu';
    };
  MailRuGroup.prototype.numberOfUsers = 100; 
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  
  var
    mailRu = new MailRu(),
    mailRuGroup = new MailRuGroup();
  
  MailRu.prototype.numberOfUsers = 10;
  ```
  
  ```javascript
  1. mailRuGroup.numberOfUsers === mailRu.numberOfUsers
  ```
  ```javascript
  2. mailRu.numberOfUsers === 10
  ```
  ```javascript
  3. mailRu instanceof MailRuGroup
  ```  
  ```javascript
  4. mailRuGroup instanceof MailRuGroup
  ```
  ```javascript
  5. mailRuGroup.constructor.prototype === mailRu.constructor.prototype
  ```    
  
  *Правильные ответы:* **2, 3, 4, 5**
    
4. Какие из ниже перечисленных выражений истинны.
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
    },
    MailRu = function () {
      this.name = 'MailRu';
    };
  MailRuGroup.prototype.numberOfUsers = 100; 
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  
  var
    mailRu = new MailRu(),
    mailRuGroup = new MailRuGroup();
  
  MailRu.prototype.numberOfUsers = '100';
  ```
  
  ```javascript
  1. mailRuGroup.numberOfUsers === mailRu.numberOfUsers
  ```
  ```javascript
  2. mailRu.numberOfUsers === 100
  ```
  ```javascript
  3. mailRu instanceof MailRuGroup
  ```  
  ```javascript
  4. mailRu.constructor.prototype.numberOfUsers === mailRuGroup.numberOfUsers
  ```
  ```javascript
  5. mailRu.name === mailRu.constructor.name
  ```    
  
  *Правильные ответы:* **3, 4**
    
5. Какие из ниже перечисленных выражений истинны.
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
    },
    MailRu = function () {
      this.name = 'MailRu';
    };
  MailRuGroup.prototype.numberOfUsers = 100; 
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  
  var
    mailRu = new MailRu(),
    mailRuGroup = new MailRuGroup();
  
  MailRu.numberOfUsers = 1;
  ```
  
  ```javascript
  1. mailRuGroup.numberOfUsers === mailRu.numberOfUsers
  ```
  ```javascript
  2. mailRu.numberOfUsers === 1
  ```
  ```javascript
  3. mailRu instanceof MailRuGroup
  ```  
  ```javascript
  4. mailRu.constructor.numberOfUsers === 1
  ```
  ```javascript
  5. mailRu.name === 'MailRu'
  ```    
  
  *Правильные ответы:* **1, 3**
  
### Тема 2. 