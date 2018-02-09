## Environments

### Production
|Property|Value|
|-|-|
|Site|[[https://kami.paragita.com]]|     
|Physical|bellatrix.pojoksantai.com|
|Database|paragita|
|Schema|production|
|User|paragita_prod|
|Branch|master|

Sitenya belum jelas mau yang mana.

### Simulation
|Property|Value|
|-|-|
|Site|[[https://sim.paragita.com]]|
|Physical|bellatrix.pojoksantai.com|
|Database|paragita|
|Schema|simulation|
|User|paragita_sim|
|Branch|simulation|

### Testing
|Property|Value|
|-|-|
|Site|[[https://test.paragita.com]]|
|Physical|bellatrix.pojoksantai.com|
|Database|paragita|
|Schema|testing|
|User|paragita_test|
|Branch|testing|

### Development
|Property|Value|
|-|-|
|Site|[[https://devel.paragita.com]]|
|Physical|aldebaran.ferdi.id|
|Database|paragita|
|Schema|development|
|User|paragita_devel|
|Branch|development|

## SMS Gateway

| Vendor | Price per SMS (IDR) | Note |
| - | - | - |
|<https://www.clickatell.com/>|270|berdasarkan simulasi, 100 sms rentang harga 2 dolar. blm tahu fitur|
|<https://wavecell.com/>|350| #N/A |
|<https://raja-sms.com/sms-masking/>|lihat di kiri|#N/A|
|<https://www.gosmsgateway.com/prices.php>| mahal | Mesti paketan |
|<https://www.aksimaya.co.id/smsgateway/>| murah ni | bisa per 3 bulan |
|<https://www.nexmo.com/pricing>| mahal | #N/A |

## Let's Encrypt Workflow

1. List all hostname from Environments
2. Update to spreadsheet
3. Check discrepancy, if not exist, create first in CloudFlare (both hostname and _acme-challenge)
4. Generate certificate, update DNS using this helper <https://github.com/ferdisn/CloudFlareAPIv4>