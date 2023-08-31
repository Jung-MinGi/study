```java
package com.min.aaaa.singleton;


public class John {
    private static John instance = new John();
    private John(){}
    public static John getInstance(){
        return instance;
    }
}

```
```java
package com.min.aaaa.singleton;

import org.assertj.core.api.Assertions;
import org.junit.jupiter.api.Test;


public class SingletonTest {
    @Test
    public void singletonTest(){
        John instance1 = John.getInstance();
        John instance2 = John.getInstance();

        Assertions.assertThat(instance1).isSameAs(instance2);
    }
}

```
* 소프트웨어 디자인 형태 중 하나로 생성된 클래스 인스턴스 하나로 돌려쓰는 형태
