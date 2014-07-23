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
  
### Тема 2. prototype
1. Что будет в результате выполнения функции?
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
      this.country = 'Russia';
    },
    MailRu = function () {
      MailRuGroup.call(this);
      this.name = 'MailRu';
    };
  MailRuGroup.prototype.getTitle = function () {
    return this.name + ' in ' + this.country;
  };
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  MailRuGroup.prototype.getTitle = function () {
    return this.name;
  };
  var mailRu = new MailRu();
  console.log(mailRu.getTitle());
  ```
  1. MailRu in Russia
  2. MailRuGroup in Russia
  3. MailRu
  4. MailRuGroup
  5. undefined

  *Правильные ответы:* **3**
  
2. Что будет в результате выполнения функции?
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
      this.country = 'Russia';
    },
    MailRu = function () {
      this.name = 'MailRu';
      MailRuGroup.call(this);
    };
  MailRuGroup.prototype.getTitle = function () {
    return this.name + ' in ' + this.country;
  };
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  MailRuGroup.prototype.getTitle = function () {
    return this.name;
  };
  var mailRu = new MailRu();
  console.log(mailRu.getTitle());
  ```
  1. MailRu in Russia
  2. MailRuGroup in Russia
  3. MailRu
  4. MailRuGroup
  5. undefined

  *Правильные ответы:* **4**
  
3. Что будет в результате выполнения функции?
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
      this.country = 'Russia';
    },
    MailRu = function () {
      MailRuGroup.call(this);
      this.name = 'MailRu';
      this.getTitle = function () {
        return this.name + ' in ' + this.country;
      };
    };
  MailRuGroup.prototype.getTitle = function () {
    return this.name + ' in ' + this.country;
  };
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  MailRuGroup.prototype.getTitle = function () {
    return this.name;
  };
  var mailRu = new MailRu();
  console.log(mailRu.getTitle());
  ```
  1. MailRu in Russia
  2. MailRuGroup in Russia
  3. MailRu
  4. MailRuGroup
  5. undefined

  *Правильные ответы:* **1**

4. Что будет в результате выполнения функции?
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
      this.country = 'Russia';
    },
    MailRu = function () {
      this.name = 'MailRu';
      MailRuGroup.call(this);
      this.getTitle = function () {
        return this.name + ' in ' + this.country;
      };
    };
  MailRuGroup.prototype.getTitle = function () {
    return this.name + ' in ' + this.country;
  };
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  MailRuGroup.prototype.getTitle = function () {
    return this.name;
  };
  var mailRu = new MailRu();
  console.log(mailRu.getTitle());
  ```
  1. MailRu in Russia
  2. MailRuGroup in Russia
  3. MailRu
  4. MailRuGroup
  5. undefined

  *Правильные ответы:* **2**

5. Что будет в результате выполнения функции?
  ```javascript
  var
    MailRuGroup = function () {
      this.name = 'MailRuGroup';
      this.country = 'Russia';
    },
    MailRu = function () {
      this.name = 'MailRu';
      MailRuGroup.call(this);
      this.getTitle = function () {
        return this.name + ' in ' + this.country;
      };
    };
  MailRuGroup.prototype.getTitle = function () {
    return this.name + ' in ' + this.country;
  };
  function F() {};
  F.prototype = MailRuGroup.prototype;
  MailRu.prototype = new F;
  MailRuGroup.prototype.getTitle = function () {
    return this.name;
  };
  var mailRu = new MailRu();
  delete mailRu.getTitle;
  console.log(mailRu.getTitle());
  ```
  1. MailRu in Russia
  2. MailRuGroup in Russia
  3. MailRu
  4. MailRuGroup
  5. undefined

  *Правильные ответы:* **4**

### Тема 3. Конструктор и приватные переменные.
1. Какие из ниже перечисленных выражений истинны.
  ```javascript
  function MailRu() {
      var data = {
        name: 'MailRu',
        headOffice: 'Moscow'
      };
      this.getData = function () {
        return data;
      };
      return this;
    }
    MailRu.prototype.setName = function (name) {
      this.data = this.data || {};
      this.data.name = name;
    };
    var mailRu = new MailRu();
  ```
  ```javascript
  1. mailRu.getData().name === 'MailRu'
  ```
  ```javascript
  2. mailRu.getData().name === mailRu.data.name
  ```
  ```javascript
  3. mailRu.setName('MailRuGroup');
     mailRu.getData().name === 'MailRuGroup'
  ```
  ```javascript
  4. mailRu.data === undefined
  ```
  ```javascript
  5. mailRu.getData().name = 'MailRuGroup'
     mailRu.getData().name === 'MailRuGroup'
  ```   

  *Правильные ответы:* **1, 4, 5**

2. Какие из ниже перечисленных выражений истинны.
  ```javascript
    function MailRu() {
      var data = {
        name: 'MailRu',
        headOffice: 'Moscow'
      };
      this.getData = function () {
        return data;
      };
      this.getName = function () {
        return data.name;
      }
      return this;
    }
    MailRu.prototype.setName = function (name) {
      this.data = this.data || {};
      this.data.name = name;
    };
    var mailRu = new MailRu();
  ```
  ```javascript
  1. mailRu.getData().name === mailRu.getName()
  ```
  ```javascript
  2. mailRu.getName() === mailRu.data.name
  ```
  ```javascript
  3. mailRu.setName('MailRuGroup');
     mailRu.getName() === 'MailRuGroup'
  ```
  ```javascript
  4. mailRu.data === undefined
  ```
  ```javascript
  5. mailRu.getData().name = 'MailRuGroup'
     mailRu.getName() === 'MailRuGroup'
  ```   

  *Правильные ответы:* **1, 4, 5**

3. Какие из ниже перечисленных выражений истинны.
  ```javascript
    function MailRu() {
      var data = {
        name: 'MailRu',
        headOffice: 'Moscow'
      };
      this.getData = function () {
        return {
          name: data.name,
          headOffice: data.headOffice
        };
      };
      this.getName = function () {
        return data.name;
      }
      return this;
    }
    MailRu.prototype.setName = function (name) {
      this.data = this.data || {};
      this.data.name = name;
    };
    var mailRu = new MailRu();
  ```
  ```javascript
  1. mailRu.getData().name === mailRu.getName()
  ```
  ```javascript
  2. mailRu.getName() === mailRu.data.name
  ```
  ```javascript
  3. mailRu.setName('MailRuGroup');
     mailRu.getName() === 'MailRuGroup'
  ```
  ```javascript
  4. mailRu.data === undefined
  ```
  ```javascript
  5. mailRu.getData().name = 'MailRuGroup'
     mailRu.getName() === 'MailRuGroup'
  ```   

  *Правильные ответы:* **1, 4**

4. Какие из ниже перечисленных выражений истинны.
  ```javascript
    function MailRu() {
      var data = {
        name: 'MailRu',
        headOffice: 'Moscow'
      };
      this.getData = function () {
        return {
          name: data.name,
          headOffice: data.headOffice
        };
      };
      this.getName = function () {
        return data.name;
      }
      return this;
    }
    MailRu.prototype.setName = function (name) {
      this.data = this.data || {};
      this.data.name = name;
    };
    var
      mailRu = new MailRu(),
      _mailRu = MailRu();
  ```
  ```javascript
  1. mailRu.getData().name === _mailRu.getName()
  ```
  ```javascript
  2. mailRu.getData() === _mailRu.getData()
  ```
  ```javascript
  3. mailRu.setName(_mailRu.getName());
     mailRu.data.name === _mailRu.getName()
  ```
  ```javascript
  4. mailRu.getName() === _mailRu.getName()
  ```
  ```javascript
  5. mailRu.getData().name = 'MailRuGroup'
     mailRu.getName() === 'MailRuGroup'
  ```   

  *Правильные ответы:* **1, 3, 4**

5. Какие из ниже перечисленных выражений истинны.
  ```javascript
    function MailRu() {
      var data = {
        name: 'MailRu',
        headOffice: 'Moscow'
      };
      this.getData = function () {
        return {
          name: data.name,
          headOffice: data.headOffice
        };
      };
      this.getName = function () {
        return data.name;
      }
      return this;
    }
    MailRu.prototype.setName = function (name) {
      this.data = this.data || {};
      this.data.name = name;
    };
    var
      mailRu = new MailRu(),
      _mailRu = MailRu.call(mailRu);
  ```
  ```javascript
  1. mailRu.getData().name === _mailRu.getName()
  ```
  ```javascript
  2. mailRu.getData() === _mailRu.getData()
  ```
  ```javascript
  3. mailRu.setName(_mailRu.getName());
     mailRu.data.name === _mailRu.getName()
  ```
  ```javascript
  4. mailRu === _mailRu
  ```
  ```javascript
  5. mailRu.setName('MailRuGroup');
     _mailRu.data.name === 'MailRuGroup';
  ```   

  *Правильные ответы:* **1, 3, 4, 5**
                    