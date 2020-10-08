# Email Finder

> Response:

```json
{
  "data": {
    "email": "satya@microsoft.com",
    "name": "Satya Nadella",
    "domain": "microsoft.com",
    "status": "deliverable",
    "accept_all": false
  }
}
```

The Email Finder API endpoint allows you to find emails programmatically. It returns an email based on a name and a domain name.

### HTTP Request

`POST https://api.coldlead.io/v1/finder`

### Parameters

Parameter | Required | Description
--------- | ------- | -----------
name | true | The name of your lead. Example: Satya Nadella
domain | true | The domain name of the company, used for emails. Example: "microsoft.com".

### Response Detail

Key | Type | Value
--------- | ------- | -----------
email | String | Normalized version of the provided email address.
name | String | The name of your lead.
domain | String | The domain of the provided email address.
accept_all | Boolean | Accept all means the domain of the email accept all emails sent to any mailbox. So, we cant't confirm if it really exists or not.
status | String | <span class="badge-status success" data-tooltip="Deliverable means ColdLead.io has confirmed the mailbox exists and the email addresses are safe to send.">deliverable</span><span data-tooltip="A risky result means the email addresses appears to exist, but have quality issues that may result in low engagement or a bounce. Use caution when sending to risky addresses. Accept-All, Disposable, and Role addresses are classified as Risky" class="badge-status energize">risky</span><span data-tooltip="Unknown occurs when ColdLead.io is unable to get a valid response from the recipient's email server. This usually happens when the destination email server is too slow or temporarily unavailable." class="badge-status black">unknown</span>
