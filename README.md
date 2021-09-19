# Emma's Portfolio Website 🎟 <br>

# 🤹🏻 Introduce 🤹🏻‍♀️
<br>

- My unique website that shows who I am and my ability I have as a front-end engineer 
<br>

https://user-images.githubusercontent.com/80943394/133916876-dfd19ef7-c325-4815-a305-c06399dfc9c2.mov

# 🔸 Main function 🔸

## 1. ScrollIntoView()
### Function 
- When click 'navbar menu item' , move to certain section which has same 'id'
<br>

<img width="798" alt="스크린샷 2021-09-19 오후 1 58 26" src="https://user-images.githubusercontent.com/80943394/133917067-39a10276-f370-49be-82b7-7606428d4d75.png">

- add data-link="id" info in each of navbar menu items which is correspond 'id' of sections in html
- then make function scrollIntoview()
### bug💥
- when evoke scrollIntoView event to contactMe button & arrow-up button, navbar menu items wasn't able to be active correctly.
- so I added function 'selectNavItem()' which is made from 'IntersectionObserver' into function scrollIntoview()
- finally when click navbarmenu,homecontact,arrow up button, navbar menu item was able to be active correctly. 

### Then what is the  function 'selectNavItem()'❓ you can see down below😆
<br>

## 2.Intersection Observer 🌈⭐️
### Function
- when scrolling window, navbar memu items to be active by noticing some inersection change using 'Intersection observer API'
### For more great performence I made Intersection observer API
<br>

### Bad for performence example (without intersection observer) 💩

<img width="1320" alt="스크린샷 2021-09-19 오후 7 26 06" src="https://user-images.githubusercontent.com/80943394/133924063-70f66e0f-88fd-4bd7-91ad-54a3c200af87.png">

1. 
