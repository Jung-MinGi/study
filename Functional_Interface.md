## java.util.function

1. Interface Consumer<T>
> 입력은 있지만 반환값은 없는 함수형 인터페이스
```
Consumer<Integer> c = i-> System.out.println("i = " + i);
c.accept(100);
```

2. Interface Function<T,R>
> 입력과 반환값이 모두 있는 함수형 인터페이스
```
public class functional {
    @Test
    void functionalTest(){
        Function<String[], List<String>> f = (String...aa)->{
            List<String> list = new ArrayList<>();
            for (String string : aa) {
                list.add(string);
            }
            return list;
        };
        List<String> apply = f.apply(new String[]{"AA", "BB", "CC"});
       Assertions.assertThat(apply.size()).isEqualTo(3);
    }
}
```

3. Interface Predicate<T>
> 입력이 있고 반환타입이 boolean인 함수형 인터페이스
```
  @Test
    void functionalTest(){
        Predicate<Integer> p = i -> i%2==0;
        boolean test = p.test(100);
        Assertions.assertThat(test).isInstanceOf(Boolean.class);
    }
```

4. Interface Supplier<T>
> 입력은 없고 반환값이 존재하는 함수형 인터페이스
```
 @Test
    void functionalTest(){
        Supplier<Integer> s = ()->Integer.parseInt("100");
        Assertions.assertThat(s.get()).isEqualTo(100);
    }
```
