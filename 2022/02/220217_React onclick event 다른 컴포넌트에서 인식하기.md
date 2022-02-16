# React onclick event 다른 컴포넌트에서 인식하기
헤더에서 '내가찜한사진' 버튼을 클릭하면 아래에 찜한 사진의 리스트가 나오게 하고 싶었다.
하지만 버튼은 'Header' 컴포넌트에 있었고 목록을 나오게 하는 건 'PostList'에서 해주어야 했기 때문에 해당 이벤트를 어떻게 넘겨줄 것인지에 대한 고민을 했다.

그러던 중, 클릭 이벤트 자체를 스토어에 저장해서 useSelector로 받아주면 되지 않을까 하는 생각을 했고, 클릭 이벤트가 발생할 때 바로 액션생성함수 -> 리듀서로 넘어가도록 dispatch 해주었다.

```javascript
const myLike = () => {
    dispatch(likeActions.callLike());
  }
```

리듀서에서 click 초기값을 false로 주고, 리듀서에 도착하면 click의 상태에 따라 true/false가 변환되어 저장되도록 만들었다.

```javascript
[CALL_LIKE] : (state, action) => produce(state, (draft)=> {
          draft.click = draft.click===true?false:true;
          console.log('버튼클릭 테스트', draft.click)
      }),
```

마지막으로, PostList 컴포넌트에서 useSelector로 click 값을 받아주고, useEffect를 써서 클릭할 수 있게 만들어주었다.

``` javascript
React.useEffect(() => {
        if(!likeButton){
          console.log('전체사진볼거야')
          dispatch(postActions.getPostFB());
        }
        else {
          console.log('내가찜한사진볼거야')
          dispatch(likeActions.setLikeFB());
        }
      // }
}, [likeButton]);
```


완성!!!