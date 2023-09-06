## 객체 생성을 자식 클래스가 결정하도록 하는 패턴
```java 
//부모 팩토리 
public  abstract class DataFactory<Y> {
    Y getEntity(){
        return createEntity();
    }
    List<Y> getEntityList(){
        ArrayList<Y> list = new ArrayList<>();
        list.add(createEntity());
        list.add(createEntity());
        list.add(createEntity());
        return list;}
   abstract Y createEntity();
}
```
```java
package com.min.aaaa.factoryMethod;
//DataFactory를 상속하는 팩토리
public class ChildFactory extends DataFactory<Tree> {
    @Override
    Tree createEntity() {//자식 레벨에서 객체 생성 
        return Tree.builder()
                .name("소나무")
                .height(300)
                .build();
    }
}

```
## @ParameterizedTest && @MethodSource
```java
package com.min.aaaa.factoryMethod;

import org.assertj.core.api.Assertions;
import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.Arguments;
import org.junit.jupiter.params.provider.MethodSource;

import java.util.stream.Stream;

public class FactoryMethodTest {
    @ParameterizedTest//여러개의 데이터들을 한번에 테스트 가능 
    @MethodSource("getEntity")
    public void factoryMethodTest(Tree tree, String expectedName) {
        Assertions.assertThat(tree.getHeight()).isEqualTo(Integer.parseInt(expectedName));
    }

    public static Stream<Arguments> getEntity() {
        return Stream.of(Arguments.arguments(Tree.builder().name("소나무1").height(100).build(), "100")
        ,Arguments.arguments(Tree.builder().name("소나무2").height(200).build(), "200")
        ,Arguments.arguments(Tree.builder().name("소나무3").height(500).build(), "500"));
    }
}
```
