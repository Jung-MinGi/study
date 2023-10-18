## 캡슐화 (encapsulation)
> 객체의 상태와 행위를 한곳에 모아두는 것

1. 접근 한정자를 이용한 캡슐화
```java
//public
//외부에서 접근 가능

//private
//외부에서 접근 불가능

//protected
//동일패키지 또는 상속하는 자식 클래스에서 접근 가능

//default
//동일패키지에서 접근 가능
```
## 상속 (inheritance)
> 자식클래스가 부모클래스의 기능을 그대로 물려받는것
> 
> Java의 모든 클래스는 Object클래스의 자식이다
> 
> 자식이 부모의 메서드를 대체할때는 override할 수 있다.
> 

## 추상화 (abstract)
> 공통된 메서드나 필드를 모아서 클래스를 만드는 것이다.
> 
> 부모 타입으로 다양한 활용 가능

##  다형성 (polymorphism)
> 자바에서는 다중 상속이 불가능해, 추상클래스로는 다형성을 구현할 수 없다.
> 
> 인터페이스를 활용해서 다중 상속을 구현할 수 있다.
```
public class ArrayList<E> extends AbstractList<E>
        implements List<E>, RandomAccess, Cloneable, java.io.Serializable
{...}

/*
        AbstractList<Integer> list1 = new ArrayList<>();
        Cloneable list2 = new ArrayList<>();
        List<Integer> list3 = new ArrayList<>();
        RandomAccess list4 = new ArrayList<>();
        Serializable list5 = new ArrayList<>();

new ArrayList는 다양하게 사용될 수 있다
*/
```
