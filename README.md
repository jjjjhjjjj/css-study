# CSS 정리

### CSS

1. #### 선택자
    - 자식 선택자 : >
    - 자손 선택자 : 공백
    - 형제 선택자 : + (전부), ~(하나)
    - 구조적 가상 클래스 : first-child, last-child, nth-child(n)
    - 동적 가상 클래스 : hover, focus, active
    - 우선순위 : 1th ID, 2th Class, 3th Tag, 0th Inline Style, -1th !important
    
2. #### Box Model
    - content, padding, border, margin으로 구성되어 있음
    - content : 가로는 width, 세로는 height
    - padding : content와 border 사이의 공간(안쪽여백)
    - border : 테두리
    - margin : 요소와 요소사이의 간격(바깥 간격)
    
3. #### Box Sizing
    - 사이즈의 기준이 되는 값
    - content-box | border-box
    
    ```css
    * {
      box-sizing : border-box;
    }
    ```
  
4. #### Box Type -> Display
    - Block -> **길막, 면**
        - Width를 선언하지 않은 경우, width = 부모의 content-box의 100%
        - 따로 width를 선언한 경우, 남은 공간은 margkn으로 자동 채움
        - Height를 선언하지 않은 경우, 자식 요소의 height 합 = 부모의 height
        - `margin-left : auto` : 자동으로 생기는 margin을 왼쪽으로
        - `margin: 0 auoto`로 가운데 정렬 가능
        - width, height, padding, border, margkn 전부 사용 가능
        
    - Inline -> **흐름, 선**
        - width, height, *-top, *-bottom 사용 불가
        
    - Inline Block
        - Block & Inline
        
5. #### Float
    - 가로배치를 하기 위해서 사용함
    - float 사용 시, 블럭 요소는 무조건 'BLOCK' 
    - 그러나 길막 못함 : 자동 width, margin 안생김 + css 깨짐
    ```css
      overflow: hidden; // 부모 요소
      
      [부모클래스]::after {
        content: '';
        display: block; //clear 값은 block에만 사용 가능
        clear: both;
      }
    ```
   
6. #### Position
    - 어떤 종류 & 기준점 확인
        - static 
        - relative : 본인 위치 기억·기준
        - absolute : float랑 비슷, position이 static이 아닌 요소를 기준으로 잡음 (보통 relative로 감쌈)
        - fixed : viewport 사이즈 기준
        
7. #### Flex
    - 선언 : `display: flex; //부모에게 `
    - 가로|세로 정렬 : `flex-direction : row | column | row-reverse | column-reverse ;`
    - 한줄|여러줄 정렬 : `flex-wrap : nowrap | wrap ;`
    - 메인축 정렬 : `justify-content`
    - 크로스축 기준 : `align-items(선), align-content(후)`
    - 순서 : `order`
    
8. #### Media Query
    - 반응형 웹! (HTML View port 선언 + Css Media Query)
    ```css
    @media screen and (min-width: 768px) {
    }
    ```
    - vw, vh : 뷰포트 기준 단위
    
9. #### Typography
    - px : 절대단위 || em, rem : 상대단위
    - em : 실제로 적용된 폰트 사이즈 단위
    - rem : root em, html에 적용된 폰트 사이즈 
    
10. #### background
    - `background-color : hex | rgb | rgba `
    - `background-image: url() `
    - `background-repeat : repeat | no-repeat `
    - `background-size: contain | cover | custom `
    - `background-position: x y `
    
11. #### Transition
    - property duration(1,000ms = 1s) [timing-function] [delay]
    - [timing-function] : ease-in | ease-out | ease-in-out | [cubic-bezier()](https://cubic-bezier.com/#.17,.67,.83,.67)
    
12. #### Animation
    ```css
    @keyframes [name] {
      from {
      }
      
      to {
      }
    }
    ```
    - from-to와 %로 조절 가능
    - animation-[name, duration, timing-function, delay, iteration-count, direction]
    
13. #### Box-shadow
    - x축 y축 흐린정도 그림자사이즈 색상
    - [box shadow generator](https://cssgenerator.org/box-shadow-css-generator.html)
    
14. #### Overflow
    - visible | auto | scroll | hidden
    
15. #### Transform
    - translate() | scale() | rotate()
    - 다른 요소들에게 영향 안줌
