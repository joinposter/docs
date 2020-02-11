## settings.getAllSettings: Account Settings

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/settings.getAllSettings'
 . '?token=687409:4164553abf6a031302898da7800b59fb';

$data = sendRequest($url);
```

> Response example:

```json
{
    "response": {
        "COMPANY_ID": "demo",
        "FIZ_ADRESS_CITY": "joinposter.com",
        "FIZ_ADRESS_PHONE": "74993466863",
        "uses_tables": 1,
        "uses_cash_shifts": 1,
        "uses_taxes": 1,
        "uses_multiprice": 0,
        "tip_amount": 10,
        "uses_bookkeeping": 1,
        "uses_ipay": 0,
        "uses_manufacturing": 0,
        "uses_quick_waiter": 0,
        "company_name": "Демо-версия Poster",
        "company_type": 1,
        "timezones": "Europe/Kiev",
        "logo": "/upload/pos_cdb_4/icon.png",
        "lang": "ru",
        "pos_phone": "74993466863",
        "analytics_plus_time": 0,
        "uses_fiscality": 0,
        "print_fiscal_by_default": 0,
        "currency": {
            "currency_id": 1,
            "currency_name": "Гривна",
            "currency_code": "грн.",
            "currency_symbol": "₴",
            "currency_code_iso": "UAH"
        },
        "email": "root@joinposter.com",
        "name": "Demo"
    }
}
```

The method returns the account settings data

### HTTP GET request

`https://joinposter.com/api/settings.getAllSettings`

### The settings.getAllSettings response parameters

Parameter | Description
--------- | -----------
COMPANY_ID | Account name
FIZ_ADRESS_CITY | Location address
FIZ_ADRESS_PHONE | Location phone number
uses_tables | The status of the table plan being used: 0—not used, 1—used
uses_cash_shifts | The status of register shifts being used: 0—not used, 1—used
uses_taxes | The status of taxes being used: 0—not used, 1—used
uses_multiprice | The status of different prices being used at different locations: 0—not used, 1—used
tip_amount | Service fee
uses_bookkeeping | The status of accounting being used: 0—not used, 1—used
uses_ipay | The status of the iPay payment method being accepted: 0—not accepted, 1—accepted
uses_manufacturing | The status of manufacturing being used: 0—not used, 1—used
uses_quick_waiter | The status of a quick waiter shift being used: 0—not used, 1—used
company_name | Location name
company_type | Location type: 1—cafe, 2—store
timezones | Time zone
logo | Link to the account logo
lang | Language in the ISO 639 format. The Ukrainian language is designated as `ua`.
pos_phone | Account owner phone number
analytics_plus_time | Business time of the location working time end
uses_fiscality | The status of fiscalization being used: 0—not used, 1—used
print_fiscal_by_default | The status of receipts for tax purposes being printed by default: 0—not printed, 1—printed
email | Account owner email
name | Account owner name
currency | Account сurrency

Inside the currency element, there is an array, each element of which contains the following properties:

Parameter | Description
--------- | -----------
currency_id | Currency ID in Poster
currency_name | Currency name
currency_code | Currency code on the register
currency_symbol | Unicode currency symbol; for the ruble, dram, and manat, HTML comes displayed on the register as a currency icon
currency_code_iso | Digital currency code according to the ISO 4217 standard

