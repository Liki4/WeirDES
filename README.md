# WeirDES

> WeirDES is golang version of a des encryption algorithm
>
> This was originally a JavaScript/Java code written in 2006[^1][^2]

[^1]: [ECNU-outline-downloader/src/des.ts](https://github.com/fun4wut/ECNU-outline-downloader/blob/master/src/des.ts)
[^2]: [jeesite4/common/src/main/java/com/jeesite/common/codec/DesUtils.java](https://github.com/thinkgem/jeesite4/blob/v5.0_dev/common/src/main/java/com/jeesite/common/codec/DesUtils.java)

## Example

```go
package main

import (
        "fmt"

        "github.com/Liki4/weirdes"
)

func main() {
        plt := "Peering is also possible using OpenVPN/GRE/..., contact me via Telegram(prefer)/Email :-)"
        fK, sK, tK := "ONLINE | lv1 - Las Vegas, US", "ONLINE | la1 - Los Angeles, US", "ONLINE | fm1 - Fremont, US"

        enc := weirdes.StrEnc(plt, fK, sK, tK)
        dec := weirdes.StrDec(enc, fK, sK, tK)

        fmt.Printf("encoded:\t%s\nplaintext:\t%s", enc, dec)
}

// encoded:        5BA75C591DA0BABA09EB6126C004AE685F91A05774AA8C5CECCAF07C33EF30342D8BE6765C13AE6C299D2C7FAAC80DB2E8FF40A17118EF1E074B889ED886CA87703858A88000BEE174A84AAD5EBF619187C6789E9E13E46146BE9C32937D1295BEEFB22D7DB3AC1C394A92DF07FBA0235D8DA8A40E3E64FF63E5F64278DDDBA8CBD0BF46F68C592A2B77D5DC21097364762CEB5C4DC1625D7E53658A46F554A82630E67042CFE5FF51CE6FCAA51B1FF4C1576EE3D845B01A
// plaintext:      Peering is also possible using OpenVPN/GRE/..., contact me via Telegram(prefer)/Email :-)
```
