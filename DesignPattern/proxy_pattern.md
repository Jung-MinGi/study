1. 실제 객체에 접근을 제어할 수 있음
2. 기존의 코드를 변경하지 않는(OCP원칙을 지킴)
3. 당장 필요하지않는 객체에 대해 인스턴스화를 지연시킬 수 있다
```java
package com.min.aaaa.proxy;

public interface BankServiceForClient {
    void withDraw();
}

```
```java
package com.min.aaaa.proxy;
//real subject
public class BankService implements BankServiceForClient{
    @Override
    public void withDraw() {
        System.out.println("현금 인출 중..");
    }
}

```
```java
package com.min.aaaa.proxy;

public class ProxyBankService implements BankServiceForClient {
    private BankServiceForClient service = new BankService();
    @Override
    public void withDraw() {
    // 이 레벨에서 실제 객체의 메서드를 호줄 하기 전후로 다양한 작업이 가능하다
        service.withDraw();
    }
}

```
```java
package com.min.aaaa.proxy;

public class Client {
    public static void main(String[] args) {

        BankServiceForClient proxyBankService = new ProxyBankService();
        proxyBankService.withDraw();
    }
}
```
