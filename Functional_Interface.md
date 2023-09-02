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
Function<String[], List<String>> f = (String...aa)->{
            List<String> list = new ArrayList<>();
            for (String string : aa) {
                list.add(string);
            }
            return list;
        };
        List<String> apply = f.apply(new String[]{"AA", "BB", "CC"});
        System.out.println("apply = " + apply);
```
