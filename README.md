# Emma's Portfolio Website 💃🍃 <br>

### 🔸 This is my unique website that shows who I am 🔸
<br>

https://user-images.githubusercontent.com/80943394/133916876-dfd19ef7-c325-4815-a305-c06399dfc9c2.mov

## 🔸 Main function 🔸
<br>

### 1. ScrollIntoView()
### When click 'navbar menu items' ,scroll to section which has same 'id'
<br>

<img width="798" alt="스크린샷 2021-09-19 오후 1 58 26" src="https://user-images.githubusercontent.com/80943394/133917067-39a10276-f370-49be-82b7-7606428d4d75.png">

- data-link="id" in each of navbar menu items which is correspond 'id' of sections in html
- Make function scrollIntoview()
### bug💥
- when evoke scrollIntoView event, navbar menu items(border) wasn't able to be active correctly.
- since I made another scroll event(InterSectionObserver).
- when evoke scrollIntoView, another scroll event also works 
- so I added function 'selectNavItem()' which is made from 'IntersectionObserver' into function scrollIntoview()
- finally when click navbarmenu,homecontact,arrow up button, navbar menu was able to be active correctly. 

### Then what is the  function 'selectNavItem()'❓ you can see down below😆
