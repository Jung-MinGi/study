```
package com.min.aaaa.strategy;

public interface Crypto {
     Integer showPrice();
}

```
```
package com.min.aaaa.strategy;

public class ShowCryptoPriceService {
    public Integer service(Crypto crypto) {
        return crypto.showPrice();
    }
}

```
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
