## Глава 2. Обработка событий
### Тема 1. Назначение обработчика событий
1. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter++;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 1
  3. 2
  4. 3
  5. 4

  *Правильные ответы:* **5**
  
2. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter++;
      };
      button.addEventListener('click', function () {
          counter--;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 2
  3. 3
  4. 1
  5. -1
  
  *Правильные ответы:* **2**
  
3. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter = 0;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 0
  3. 2
  4. 3
  5. 1
  
  *Правильные ответы:* **4**
  
4. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter = 0;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter += 2;
      }, false);
      button.addEventListener('click', function () {
          counter += 3;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 3
  3. 5
  4. 6
  5. 0
  
  *Правильные ответы:* **4**

5. Чему будет равна переменная `counter` после клика на кнопку

  ```html
  <button id="my-button">Click me</button>
  
  <script>
      var
        counter = 0,
        button = document.getElementById('my-button');
      button.onclick = function () {
          counter += 5;
      };
      button.addEventListener('click', function () {
          counter++;
      }, false);
      button.addEventListener('click', function () {
          counter -= 2;
      }, false);
      button.addEventListener('click', function () {
          counter += 3;
      }, false);
  </script>
  ```
  
  1. Будет ошибка
  2. 5
  3. 8
  4. 3
  5. 7
  
  *Правильные ответы:* **5**
  
### Тема 2. Capturing и bubbling.
1. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, false);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, false)
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **3**

2. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, true);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, true);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **4**

3. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, false);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, true);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **3**
  
4. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
          body.addEventListener('click', function() {
              console.log('body')
          }, true);
  
          div.addEventListener('click', function() {
              console.log('div')
          }, false);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **4**
    
5. Что будет в консоли после клика на `div`
  
  ```html
  <body>
      <div>This is my div</div>
  
      <script>
          var
            body = document.body,
            div = document.querySelector('div');
  
            body.addEventListener('click', function(e) {
                e.stopPropagation();
                console.log('body')
            }, false);
    
            div.addEventListener('click', function(e) {
                e.stopPropagation();
                console.log('div')
            }, false);
  
      </script>
  </body>
  ```
  1. div
  2. body
  3. div
     body
  4. body
     div
  5. пустая строка
   
  *Правильные ответы:* **1**
            