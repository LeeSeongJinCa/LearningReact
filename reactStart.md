**만약 reactApp이라는 폴더에 생성하려면**
- create-react-app test
- yarn
- yarn start

### Components(구성요소)
- components 폴더는 src 폴더 안에 생성되어야 함
- component 이름은 항상 대문자로 시작해야 함(DOM 태그로 인식하는 것을 피하기 위함)
- 붕어빵 틀 -> 붕어빵 틀만 있으면 팥 붕어빵, 슈크림 붕어빵 등 어려가지 붕어빵을 찍어낼 수 있음
- 컴포넌트를 이용해 비슷한 틀을 여러개 만들 수 있음
- Function Componets, Class Components 가 존재
``` javascript
function Welcome(props) {
    return <h1>Hello, {props.name}</h1> // function component
}
class Welcome extends React.Component {
    render() {
        return <h1>Hello, {props.name}</h1> // class component
    }
}
```

### Components 합성
- components 안에 또 다른 components를 넣을 수 있음
``` javascript
function Welcome(props) {
    return <h1>Hello, {props.name}</h1>
}
function App() {
    return (
        <div>
            <Welcome name="Lee">
            <Welcome name="Kim">
            <Welcome name="Park">
        </div>
    )
}
ReactDOM.render(
    <App />,
    document.getElementById('root');
)
```

### Props(Property, 속성)
- Components의 입력으로 Props가 들어가고 출력으로 React Elements가 나옴
- 붕어빵의 재료 -> 고구마, 팥, 슈크림 붕어빵이 나옴
- ReadOnly -> 붕어빵을 다 구웠는데 속재료를 바꿀 수 없음

### React.createElements()
``` javascript
const element = {
    type: 'h1', // 태그
    props: {
        className: 'greeting', // 클레스
        children: 'Hello, World!' // 노드 텍스트
    }
};
```

### ReactDom.render()
``` javascript
const name = 'Lee';
const element = <h1>Hello, {name}</h1>;
ReactDOM.render(
    element,
    document.getElementById('root')
);

XML/HTML
{JavascriptCode}
XML/HTML
```

### JSX
- 하나의 객체를 나타낸다.
- 따라서, elements는 하나의 객체(태그)로 전체를 감싸야 한다.
``` javascript
const element = (
    <div> // 하나의 객체
        <h1>Hello!</h1>
        <h2>Good to see you here.</h2>
    </div>
);
```

### State
- component에 대한 변경 가능한 데이터
- state는 사용자가 정의(랜더링, 데이터 흐름)
- state는 직접 수정 X (하면 안됌)
- setState()를 사용해서 수정
``` javascript
class LikeButton extends React.Component {
    constructor(props) {
        super(props);

        this.state = {
            liked: false
        }; // state 정의
    }
}
```
---
``` javascript
render() {
    if(this.state.liked) {
        return 'You liked this.';
    }
    return (
        <button onClick={() => this.setState({liked: true})}>
            Like
        </button>
    );
}
```

### Life cycle
- React component의 생명주기
1. Mounting     - 출생
2. Updating     - 인생
3. Unmounting   - 사망









