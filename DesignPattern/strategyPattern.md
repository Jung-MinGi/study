```
package com.min.aaaa.strategy;
//공통된 행위를 추상화 시켜 인터페이스로 만듦
public interface Crypto {
     Integer showPrice();
}
```
***
위의 인터페이스를 구현하는 두 개의 클래스 생성
```
package com.min.aaaa.strategy;

public class Eth implements Crypto{
    @Override
    public Integer showPrice() {
        return 2200000;
    }
}

```
```
package com.min.aaaa.strategy;

public class Btc implements Crypto{
    @Override
    public Integer showPrice() {
        return 40000000;
    }
}
```
***
```
package com.min.aaaa.strategy;

public class ShowCryptoPriceService {
    public Integer service(Crypto crypto) {
        return crypto.showPrice();
    }
}

```
***
```
package com.min.aaaa.strategy;

import org.assertj.core.api.Assertions;
import org.junit.jupiter.api.Test;

public class StrategyTest {
    @Test
    public void strategyTest(){

        ShowCryptoPriceService showCryptoPriceService = new ShowCryptoPriceService();

        Integer price1 = showCryptoPriceService.service(new Btc());
        Assertions.assertThat(price1).isEqualTo(40000000);

        Integer price2 = showCryptoPriceService.service(new Eth());
        Assertions.assertThat(price2).isEqualTo(2200000);
    }

}

```
