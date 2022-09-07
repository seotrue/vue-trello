### 중첩 라우팅
```vue

 {path: '/b/:bid', component: Home, children:[
        {path:'c/:cid', component:}
     ]},
  ]
```
### watch
- 감시하구 싶은 대상이 변경이 되면 함수 실행
```vue
watch:{
// 방법 1: 함수

'$route'() {
    this.fetchData()
}
// 방법2: 객체
'$route': {
    handler: 'fetchData',
    immediate: true // =>> 바로 즉시 실행 한다는 의미 created 함수로 같은 읠미
}
}
```
### 네비게이션 가드
- ```beforeEnter``` 라우팅 직전에 해당에 선언된 함수가 실행
```vue

 {path:'/', component: Home, beforeEnter: requireAuth}
 {path: '/b/:bid', component: Home, children:[
        {path:'c/:cid', component:}
     ]},
  ]
```
```vue
// beforeEnter는 to, from, next 세개의 인자 값을 받는다
const requireAuth = (to, from, next) => {

}
```

- this.$el : vue 컴포넌트의 dom 객체.

