---
description: Describes how folios should be handled
---

# Folio Management

Folio is a ledger where the investor's investment records are held. There are no limits on the number of folios a person can hold either on AMC or on scheme level. 

Folio creation should ideally follow a few rules to ensure that there is sanity in the system

Folio number should be unique at **AMC+Scheme+Option** Level. Example 

* ICICI Value Discovery fund growth : folio 1
* ICICI Value discovery fund dividend payout : folio 2
* ICICI Value discovery fund dividend reinvestment : folio 3

_If you are going to have goal based investing then you need to change the logic of folio number based on goals also and the new logic will be to have a unique folio number at **AMC+Scheme+Option+Goal** Level._ 

{% hint style="info" %}
Why is all this required? 

This is required because there are certain complications that come in the folio later on

* Redemption is easily managed within the system
* As per RTA, a folio cannot have both payout and reinvestment of the same scheme hence this avoids any transaction rejection later on. 
* System cleanliness is managed. 
{% endhint %}

When to allot a folio to an investor in your DB and mark as active?

This is very important because there are circumstances where in the RTA can process a transaction and then it later rejects it. In such cases making a folio redundant is very important to ensure that the next transaction of the investor goes as blank because the folio alotted against the transaction has now been made defunct by RTA

{% hint style="info" %}
Note that this is only applicable for first transaction in a scheme+option for the user. Once a transaction is successfully processed, you can keep the folio for all subsequent transactions.
{% endhint %}

Steps to save the folio number

* 1st Transaction is done by investor in the combination provided above. 
* No folio will be sent to the RTA at the time of transaction posting
* REverse feed will be received with the folio number. 
* Same folio needs to be stored and marked as active unless the first transaction is rejected by RTA. 
* From 2nd transaction onwards you send across the folio number you have saved against the scheme. 

{% hint style="info" %}
Do note that folio numbers have 2 formats at RTAs. Some AMCs have folio numbers in numeric format \( eg 123456789\) and some have a check digit also \( eg 1234567/45\). The DB you design needs to store the folio number as it is. The check digit is required to be sent while sending the transactions.
{% endhint %}





\_\_



