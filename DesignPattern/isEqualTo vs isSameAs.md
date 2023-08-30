* isEqualTo 인스턴스안의 값을 비교
* isSameAs 동일한 인스턴스인지 비교

```
package com.min.aaaa.singleton;

public class Animal {
    private String name;
    private int height;

    public Animal(String name, int height) {
        this.name = name;
        this.height = height;
    }

    public String getName() {
        return name;
    }
    public int getHeight() {
        return height;
    }
}
```
```
 @Test
    public void compare(){
        Animal 사자1 = new Animal("사자", 100);
        Animal 사자2 = new Animal("사자", 100);

        Assertions.assertThat(사자1.getHeight()).isEqualTo(사자2.getHeight());
        Assertions.assertThat(사자1).isNotSameAs(사자2);
    }
```
