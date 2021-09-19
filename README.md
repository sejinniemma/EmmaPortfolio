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
- (I added selctNavItem(target) only for navbar menu click event but not for contactME & arrow up button😩)
- so I added function 'selectNavItem()' which is made from 'IntersectionObserver' into function scrollIntoview() so that it works in 'function scrollIntoview' at once.

<img width="569" alt="스크린샷 2021-09-19 오후 8 11 21" src="https://user-images.githubusercontent.com/80943394/133925402-5f4482af-b172-490a-a36b-d95a4fbbaae5.png">

- finally when click navbarmenu,homecontact,arrow up button, navbar menu item was able to be active correctly. 

### Then How it was made function 'selectNavItem(sectionIds..?)'❓ you can see down below😆
<br>

## 2.Intersection Observer 🌈⭐️
### Function
- when scrolling window, navbar memu items to be active by noticing some inersection change using 'Intersection observer API'
- For more great performence I made Intersection observer API
<br>

### ex) Bad performence without intersection observer❌ 💩

<img width="1320" alt="스크린샷 2021-09-19 오후 7 26 06" src="https://user-images.githubusercontent.com/80943394/133924063-70f66e0f-88fd-4bd7-91ad-54a3c200af87.png">

1. getboundingClientRect() generate layout even whever scroll events (too bad)
2. we should avoid heavy things in callback function because we can't do anything until callback is finished.
3. scroll event generate so frequently.Instead we make layout in the for loop whenever scroll events,I prefer using Intersection Observer API👓

## Let's use Intersection Observer 🧬
### 1.sectionIds[] : make new 'Id' array usin 'MAP' API
- make sections and navbar menu items as a DOM element using sectionIds
- so we can control section and navbar menu more easily

<img width="930" alt="스크린샷 2021-09-19 오후 8 38 50" src="https://user-images.githubusercontent.com/80943394/133926369-093c7645-ada5-4a40-9a82-0c7dcdd3b9e4.png">

### 2.make Intersection Observer
- Intersection observer parameter : callback,options
- when intersection observer observe sections, I send callback to be active menu items
- those are possible using entry information.
<br>

<img width="803" alt="스크린샷 2021-09-19 오후 8 53 51" src="https://user-images.githubusercontent.com/80943394/133927238-0d32cee4-8620-4aa0-98d8-19fb14e5c88f.png">

- index : since we made sections and navbar menu using sectionIds using map
- so they can find current element through 'entry.target.id' 
<br>

### selectNavItem
- be active current navbar menu item and remove active class to the previous one seleted.
- so we sholud remember previous one make new variable.
- this is a function I mentioned before.
- we can use this function very useful.
- for navbar menu,contact,arrow-up, and scroll event

### bug💥
- As soon as the page loaded 'testimonial' navbar menu items was selected.
- when I debugged, intersectionRatio : 0.
- It means some sections are paged out.
- so I gave condition (intersectionRatio > 0)

### 3. When scrolling, excute intersection observer

<img width="965" alt="스크린샷 2021-09-19 오후 9 36 05" src="https://user-images.githubusercontent.com/80943394/133927804-771d419a-93d6-4f84-a7f2-423251b78231.png">

### bug💥
## 1.wheel event
- scrollIntoview event is working when scrolling.
- so whenver scrollIntoview events,selectNavItems generate. so there is a bug.
- to avoid this situation, I used 'wheel' event instead of using scroll event.
- 'wheel' is only working when person make scroll with mouse.

## 2.when window size is different
- It can happen first section (#home) and the last section(#contact) doesn't go out or come inside within document.It depends on window size.
- To prevent this,I gave some conditions using window and document properties which is very useful.
