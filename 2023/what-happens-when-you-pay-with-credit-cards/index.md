---
title: "What happens when you pay with credit cards"
date: 2023-10-21
categories:
  - "Thoughts"
tags:
  - "knowledge"
coverImage: "./images/mark-oflynn-bqjswIxbhEE-unsplash.webp"
public: true
---

Credit cards are a crucial part of our financial life. These plastic pals make payments way easier and more secure than what cash alone could offer. But what goes on behind this convenience?

<!--more-->

# The flow

When you make a charge with your card, your merchant sends an **authorisation** message to your card's issuing bank to hold an amount in your account's balance. This is why you see _pending_ status in your account.

The message doesn't go directly from the merchant to the bank, though. It goes through a card scheme network: Mastercard, Visa, etc.

At the end of the day, the merchant gathers all of these authorised charges and submit them to the respective card scheme networks. This is called **settlement** and it is when the charge is confirmed to be present in your next billing statement. Note that some merchants may not gather charges every end-of-day but usually they will not hold for more than 7 days.

The card schemes will then do their job to settle these charges with issuing banks, deducting the funds from respective cards. The merchant will also be transferred money into their account.

![](./images/credit-card-flow-simple.png)

However, merchants usually don't implement credit card processing on their own but rely on payment processors like Opn, Stripe, Adyen, etc. These payment processors are the ones who actually communicate with card schemes and perform tasks like settlement.

From now on we will use the term _payment processor_ to refer to whoever actually processes transactions and communicates with card schemes, be it merchants or payment processor services.

# ISO 8583

When payment processors and card schemes communicate, the messages don't just say, "_Hey Visa, please hold $10 on Alice's account_,": they use ISO 8583 standard.

ISO 8583 is an international standard for card payment communications. It is used by card schemes worldwide such as Mastercard, Visa and JCB.

The standard has message types that cover use cases like authorisation, reversal and settlement, just to name a few. The first two are online calls where the latter is usually a batch operation where it is run periodically.

An ISO 8583 message contains fields like message type indicator (to indicate that it is an authorisation message, a reversal message, etc.), card number, charge amount, country code, and A LOT more to cover the who-what-when-where-how of a charge as much as possible. It will even tell whether a charge is made through a point-of-sale system (POS) or made online.

# 3DS but it's not Nintendo

Ever wondered why sometimes you are required to enter an OTP to authorise a charge? This process is called 3D-Secure or 3DS. It adds an additional protection layer to combat frauds.

Your card issuer uses a number of factors to assess the risk of a charge. If your card issuer has enough information to _believe_ that this is not a fraudulent charge it may authorise your charge right away without requiring you to enter an OTP, which makes it convenient for you. This is called the _frictionless flow_.

On the other hand, if your bank asks you to confirm your purchase with an OTP, you are going through the _challenge_ flow.

# Conclusion

When you pay with your credit card, the charge is held by a payment processor before being sent to a card scheme like Visa at the end of the day or some fixed period set by the payment processor. Only then will your charge lose the _pending_ status.

There is a lot more going on behind the scenes that I did not cover, like fraud prevention and the dispute process. Luckily that is not something you have to think about when you pick up your card and swipe it at a grocery store on your way home.

_Icons by Sergey Ershov, Steve Schoger and Phosphor Icons_

_Photo by [Mark OFlynn](https://unsplash.com/@paxtechnology?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/person-holding-black-and-white-card-bqjswIxbhEE?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)_
