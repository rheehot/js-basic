- [Hoisting](#hoisting)
- [Closure](#closure)
- [Data type](#data-type)

# Hoisting

`Hoisting`은 직역하면 **끌어올리다**라는 뜻이 있다.

그러면 무엇을 끌어올릴까?

**함수 안에 있는 모든 선언을 끌어올려서 해당 함수 유효범위의 최상단에 선언**한다.

다만, 변수와 함수의 `declare`에서만 Hoisting이 발생하고, `initialize`는 발생하지 않는다.

const/let 에서는 Hoisting이 발생하지 않는다고 생각할 수 있는데,

var/const/let 모두 발생한다. 그런데 차이점이 있다.

var에서는 끌어올려진 값이 undefined를 받더라도 error 없이 실행이 되었는데,

const/let에서는 undefined를 받으면 TDZ(Temporal Dead Zone)에 의해서 제어를 받아

**Reference error**를 내보낸다. 이렇게 의도하지 않은 Hoisting을 막는다.

# Closure

`closure`는 자기 자신을 포함한 외부 함수의 인자, 지역변수들을 외부함수가 종료된 이후에도 사용가능한 변수를 뜻 하는데,

이 변수를 `자유 변수`라고 부른다. **이 것**은 `closure`로만 접근이 가능하기 때문에

객체지향 언어의 Private Method와 같은 역할로 주로 쓰인다.

    const closure = name => {
        const favorite = "pasta";
        return () => console.log(`My name is ${name}, favorite is ${favorite}`);
    };
    const print = closure("Larry Jung");
    print(); // console >> My name is Larry Jung, favorite is pasta

# Data type

JS의 `자료형`에는 **원시 타입**, **참조 타입** 두 가지가 있다.

- 원시 타입

  > undefined, null, number, string, boolean

- 참조 타입
  > Object

원시 타입은 할당될 때, 메모리 상에 고정된 크기로 저장되고,

참조 타입은 크기가 정해져 있지 않으며 할당 시 직접 저장될 수 없어 변수에는 데이터에 대한 참조만 저장된다.

참조는 데이터의 주소고, 데이터의 값이 아님.
