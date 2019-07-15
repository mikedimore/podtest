# PrizeOut iOS


### Install

To use the SDK with [CocoaPods](https://l.facebook.com/l.php?u=https%3A%2F%2Fcocoapods.org%2F%3Ffbclid%3DIwAR2pVauCjG8-WR1-IFZZh8EPpyFRjRlqL7p6fbh7tOBnV19sjGB4actFOjA&h=AT1yioUhDHlKqsfTuivNePKKALAjqDpGVR-0qxZ8054cxa0SfebNAC7MonT14Wvyr5MM8wl_gYNseE7P-jAnwHRi0kKKF-9NFTzK9qJpObNn1VotOkRyYcShKaIl8lqDvBlI6y2n), add the following lines to your Podfile:

```
use_frameworks!

pod 'PrizeOut'
```

### Use

Import `PrizeOut` and create the POUser and POPublisher objects

```
import PrizeOut

let pouser = POUser(
    firstname:  "John",
    lastname:   "Smith",
    birthYear:  "1980",
    gender:     "M",
    email:      "JSmith@example.com",
    id:         "1234",
    country:    "USA",
    region:     "us",
    balance:    "15000"  // Currency in cents
)

let pub = POPublisher(
    name:   "FleetWit",
    logo:   "https://www.fleetwit.com/theme/images/logos/FW-mark-color.png",
    id:     "12345678912345678912345678912345",
    apiKey: "12345678-1234-1234-1234-123456789123"
)
```

Once the config objects are created, display the PrizeOut interface
```
let poconfig = PrizeOutConfig(user: pouser, publisher: pub)
PrizeOutManager.launch(config: poconfig)
```

Alternatively, PrizeOutManager can return a ViewController object instead of directly launching
```
let vc =  PrizeOutManager.prizeOutViewController(config: poconfig)
self.present(vc, animated: true)
```

![PrizeOut](https://i.ibb.co/ysKL4Pr/prizeout-screen.png)
