## dash.getPaymentsReport: Billing Reports by Days/Months

> Request example:

```php
<?php
$url = 'https://joinposter.com/api/dash.getPaymentsReport'
 . '?token=687409:4164553abf6a031302898da7800b59fb'
 . '&date_from=20170501'
 . '&date_to=20170531';

$data = sendRequest($url);
```

> Response example:

```json
{
    "response": {
        "days": [
            {
                "date": "2017-05-23",
                "payed_cash_sum": "1607996",
                "payed_card_sum": "365552",
                "payed_cert_in_sum": "0",
                "payed_cert_out_sum": "0",
                "payed_bonus_sum": "0",
                "payed_incust_sum": "0",
                "payed_sum_sum": "1973548"
            },
            {
                "date": "2017-06-03",
                "payed_cash_sum": "1108969",
                "payed_card_sum": "1090915",
                "payed_cert_in_sum": "0",
                "payed_cert_out_sum": "0",
                "payed_bonus_sum": "0",
                "payed_incust_sum": "0",
                "payed_sum_sum": "2199884"
            }
        ],
        "total": {
            "payed_cash_sum": 2716965,
            "payed_card_sum": 1456467,
            "payed_third_party_sum": 0,
            "payed_cert_in_sum": 0,
            "payed_cert_out_sum": 0,
            "payed_bonus_sum": 0,
            "payed_incust_sum": 0,
            "payed_sum_sum": 4173432
        }
    }
}
```

> Response example по месяцам:

```json
{
    "response": {
        "days": [
            {
                "date": "2017-06",
                "payed_cash_sum": "27286420",
                "payed_card_sum": "1951853",
                "payed_cert_in_sum": "0",
                "payed_cert_out_sum": "0",
                "payed_bonus_sum": "0",
                "payed_incust_sum": "0",
                "payed_sum_sum": "29234560"
            },
            {
                "date": "2017-05",
                "payed_cash_sum": "60273456",
                "payed_card_sum": "6290658",
                "payed_cert_in_sum": "0",
                "payed_cert_out_sum": "0",
                "payed_bonus_sum": "0",
                "payed_incust_sum": "0",
                "payed_sum_sum": "66564114"
            },
            {
                "date": "2017-04",
                "payed_cash_sum": "49090724",
                "payed_card_sum": "4782295",
                "payed_cert_in_sum": "0",
                "payed_cert_out_sum": "0",
                "payed_bonus_sum": "0",
                "payed_incust_sum": "0",
                "payed_sum_sum": "53873019"
            }
        ],
        "total": {
            "payed_cash_sum": 136650600,
            "payed_card_sum": 13024806,
            "payed_third_party_sum": 0,
            "payed_cert_in_sum": 0,
            "payed_cert_out_sum": 0,
            "payed_bonus_sum": 0,
            "payed_incust_sum": 0,
            "payed_sum_sum": 149671693
        }
    }
}
```

The method returns the billing reports by days. If a time interval is more than 65 days, the billing reports are by months

### HTTP request

`GET https://joinposter.com/api/dash.getPaymentsReport`

### GET parameters of the dash.getPaymentsReport request

Parameter | Description
--------- | -----------
spot_id | An optional parameter, the ID of a location to return reports to
date_from | An optional parameter, the sampling start date in the `Ymd` format, inclusive. The default date is a month ago.
date_to | An optional parameter, the sampling end date in the `Ymd` format, inclusive. The default date is the current date.

### The dash.getPaymentsReport response parameters

Parameter | Description
--------- | -----------
days | List of payment days/months
total | Total amounts by all days

Inside the `days` element, there is an array, each element of which contains the following properties:

Parameter | Description
--------- | -----------
date | The date in the `Y-m-d` or `Y-m` format in the output by months
payed_cash_sum | Payment by cash in kopecks
payed_card_sum | Payment by credit card in kopecks
payed_cert_in_sum | Payment by a gift card in kopecks. It comes if the Include Payment by a Gift Card option is enabled in the management settings.
payed_cert_out_sum | Payment by a gift card in kopecks. It comes if the Include Payment by a Gift Card option is disabled in the management settings and is equivalent to a discount.
payed_bonus_sum | Payment by points
payed_incust_sum | incust payment
payed_sum_sum | The total amount of payments for the day in kopecks

Inside the `total` element, there are the following properties:

Parameter | Description
--------- | -----------
payed_cash_sum | The total amount of payments by cash in kopecks
payed_card_sum | The total amount of payments by credit card in kopecks
payed_third_party_sum | The total amount of payments by a third party
payed_cert_in_sum | The total amount of payments by a gift card in kopecks. It comes if the Include Payment by a Gift Card option is enabled in the management settings.
payed_cert_out_sum | The total amount of payments by a gift card in kopecks. It comes if the Include Payment by a Gift Card option is disabled in the management settings and is equivalent to a discount.
payed_bonus_sum | Total amount of payments by points
payed_incust_sum | Total amount of incust payments
payed_sum_sum | Total amount of all payments in kopecks

