### Linter
Usar ESLint
### Js en html
No incrustar js en html <script>...</script>. Hay que modularizar
### Let vs const
Uso correcto de let y const (se puede modificar internamente los no primitivos con const pero no puede ser otro tipo de dato, ejemplo de Array a Object)
### Dom en bubcles
No modificar el dom en un buble. La idea es repintar el DOM una sola vez
  
 Mal:

      const texts = document.getElementById('texts');
      const elements = ['a', 'b', 'c', 'd'];
      
      for (const element of elements) {
        texts.innerHTML += element;
      }


  Bien:
      
      const fragment = document.createDocumentFragment();
      
      for (const element of elements) {
        fragment.append(element);
      }
      
      texts.innerHTML += fragment;


### Get elements
Consumen más recursos
  Consume mucho:
  
      document.getElementsByTagName()
      document.getElementsByClassName()
      document.getElementsByName()
Consume poco:

      document.querySelector()
      document.querySelectorAll()   
      document.getElementById()


## Referencias
https://www.youtube.com/watch?v=9x-Y_E9VKig
