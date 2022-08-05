# CSS(Cascading Style Sheets)

## CSS란?
> Cascading Style Sheets(CSS)는 HTML이나 XML(XML의 방언인 SVG, XHTML 포함)로 작성된 문서의 표시 방법을 기술하기 위한 스타일 시트 언어입니다. CSS는 요소가 화면, 종이, 음성이나 다른 매체 상에 어떻게 렌더링되어야 하는지 지정합니다.

<br>

## 벤더 프리픽스(Vendor Prefix)

> 벤더 프리픽스(vendor prefix)란 주요 웹 브라우저 공급자가 새로운 실험적인 기능을 제공할 때 이전 버전의 웹 브라우저에 그 사실을 알려주기 위해 사용하는 접두사(prefix)를 의미합니다. <br> 아직 CSS 권고안에 포함되지 못한 기능이나, CSS 권고안에는 포함되어 있지만 아직 완벽하게 제정된 상태가 아닌 기능을 사용하고자 할 때 벤더 프리픽스를 사용하게 됩니다.<br> (출처 : tcpschool.com)

<br> 

+  주요 웹 브라우저의 벤더프리픽스
    + IE : -ms-
    + Chrome, Safari : -webkit-
    + Mozilla : -moz-
    + Opera : -o-

<br> 


```css
<style>

.button {

  background: linear-gradient(red, yellow);     <!-- CSS 표준 문법 코드 -->

  background: red;          <!-- gradient 속성을 지원하지 않는 모든 브라우저를 위한 코드 -->

  background: -webkit-linear-gradient(red, yellow); <!-- 크롬과 사파리 4.0 이상을 위한 코드 -->

  background: -moz-linear-gradient(red, yellow);    <!-- 파이어폭스 3.6 이상을 위한 코드 -->

  background: -ms-linear-gradient(red, yellow);     <!-- 익스플로러 10.0 이상을 위한 코드 -->

  background: -o-linear-gradient(red, yellow);      <!-- 오페라 10.0 이상을 위한 코드 -->  

}

</style>
```

### 단위
* 절대적인 단위(absolute unit)
  * px
* 상대적인 단위(relative unit)
  * %(퍼센트)
  * v*(뷰포트)
    * ex) 1vw = 뷰포트 너비의 1%, 1vh = 뷰포트 높이의 1%
  * em(relative to parent element) : 부모요소의 영향을 받음
  * rem(relative to root element) : 부모요소의 영향을 받지 않음(사이즈고정)

#### 단위 - 기준 1
* 부모요소의 사이즈에 따라 사이즈가 변경이 되어야 할 때 : %, em 사용
* 부모요소와 상관없이 브라우저 사이즈에 따라 반응해야 할 때 : v*, rem 사용

#### 단위 - 기준2 
* 요소의 너비와 높이에 따라 사이즈가 변경 되어야 할 때 : %, v* 사용
* 폰트사이즈에 따라 사이즈가 변경 되어야 할 때 : em, rem 사용


<br/>

## CSS 작성순서
1. Display
2. Layout
3. Visibility
4. Position
5. Box model
6. Color
7. Text
8. Animation
9. Others
10. Pseudo elements

## CSS 작성규칙(상세)

|1. Display|2. Layout|3. Visibility|4. Position|5. Box model|6. Color|
|----|----|----|----|----|----|
| 1) display <br>  2) flex-direction<br>  3) flex-wrap<br>4) justify-content<br>5) lign-content<br>6) align-items<br>7) order<br>8) flex-grow<br>9) flex-shrink<br>10) lex-basis<br>11) align-self<br> | 1) float<br />2) clear<br><br><br><br><br><br><br><br><br><br> | 1) visibility<br>2) overflow<br>3) clip<br><br><br><br><br><br><br><br><br>|1) position<br>2) z-index<br>3) top<br>4) bottom<br>5) left<br>6) right<br>7) trasnform<br><br><br><br><br>|1) box-sizing<br>2) width<br>3) min-width<br>4) max-width<br>5) height<br>6) min-height<br>7) max-height<br>8) margin<br>9) padding<br><br><br>|1) color<br>2) border<br>3) border-radius<br>4) background<br>5) box-shadow<br>6) opacity<br><br><br><br><br><br>|

|7. Text|8. Animation|9. Others|10. Pseudo elements|
|----|----|----|----|
|1) font<br>2) font-family<br>3) font-size<br>4) font-weight<br>5) font-style<br>6) font-variant<br>7) font-size-adjust<br>8) font-stretch<br>9) font-effect<br>10) font-emphasize<br>11) font-emphasize-position<br>12) font-emphasize-style<br>13) font-smooth<br>14) line-height<br>15) letter-spacing<br>16) white-space<br>17) word-break<br>18) text-overflow|1) transition<br>2) animation<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>|1) cursor<br>2) outline<br>3) outline-width<br>4) outline-style<br>5) outline-color<br>6) outline-offset<br><br><br><br><br><br><br><br><br><br><br><br><br>|1) :hover<br>2) :focus<br>3) :active<br>4) :first-child<br>5) :last-child<br>6) ::before<br>7) ::after<br><br><br><br><br><br><br><br><br><br><br><br><br>|

