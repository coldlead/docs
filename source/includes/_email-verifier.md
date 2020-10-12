# Email Verifier

> Response:

```json
{
  "data": {
    "email": "contact@coldlead.io",
    "username": "contact",
    "domain": "coldlead.io",
    "status": "deliverable",
    "reason": "accepted_email",
    "accept_all": false,
    "disposable": false,
    "role_address": true,
    "free": false
  }
}
```

This API endpoint allows you to verify the deliverability of an email address.

### HTTP Request

`GET|POST https://api.coldlead.io/v1/verify`

### Parameters

Parameter | Required | Description
--------- | ------- | -----------
email | true | Email address to verify.

### Response Detail

Key | Type | Value
--------- | ------- | -----------
email | String | Normalized version of the provided email address.
user | String | The user (mailbox) of the provided email address.
domain | String | The domain of the provided email address.
free | Boolean | Free means this email is from a free email provider such as Gmail, Hotmail, Yahoo!, etc.
accept_all | Boolean | Accept all means the domain of the email accept all emails sent to any mailbox. So, we cant't confirm if it really exists or not.
disposable | Boolean | Disposable means the mailbox exists, but is from a disposable/temporary domain.
role_address | Boolean | Role means the mailbox exists, but is a role account (contact, support, sales, admin).
status | String | <span class="badge-status success" data-tooltip="Deliverable means ColdLead.io has confirmed the mailbox exists and the email addresses are safe to send.">deliverable</span><span data-tooltip="A risky result means the email addresses appears to exist, but have quality issues that may result in low engagement or a bounce. Use caution when sending to risky addresses. Accept-All, Disposable, and Role addresses are classified as Risky" class="badge-status energize">risky</span><span data-tooltip="Unknown occurs when ColdLead.io is unable to get a valid response from the recipient's email server. This usually happens when the destination email server is too slow or temporarily unavailable." class="badge-status black">unknown</span><span data-tooltip="Undeliverable email addresses do not exist, or are syntactically incorrect." class="badge-status danger">undeliverable</span>
reason | String | <span data-tooltip="ColdLead.io has confirmed the mailbox exists and the email addresses are safe to send." class="badge-status success">accepted_email</span><span data-tooltip="Role means the mailbox exists, but is a role account (contact, support, sales, admin)." class="badge-status energize opacity-70">role</span><span data-tooltip="Accept all means the domain of the email accept all emails sent to any mailbox. So, we cant't confirm if it really exists or not." class="badge-status energize opacity-90">accept_all</span><span data-tooltip="Disposable means the mailbox exists, but is from a disposable/temporary domain." class="badge-status energize">disposable</span><span data-tooltip="Unavailable SMTP is an unknown result, because the mail server returned an unexpected and temporarily response during the verification process." class="badge-status default">unavailable_smtp</span><span data-tooltip="Timeout is an unknown result, because the mail server takes too long to answer our requests." class="badge-status black">timeout</span><span data-tooltip="No connect is an undeliverable result, because the mail server is unreachable, and is not safe to send." class="badge-status danger opacity-50">no_connect</span><span data-tooltip="Rejected email means it is undeliverable, because the provider confirmed the mailbox doesn't exists." class="badge-status danger opacity-70">rejected_email</span><span data-tooltip="Invalid domain means it is undeliverable, because the domain doesn't exists or the MX server is misconfigured." class="badge-status danger opacity-90">invalid_domain</span><span data-tooltip="Invalid email means it is undeliverable, because the email has an incorrect syntax." class="badge-status danger">invalid_email</span>
