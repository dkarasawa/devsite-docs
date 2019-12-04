---
sites_supported:
- mla
- mpe
- mco
- mlu
- mlm
- mlc
- mlb
---

# QR unattended model


## What’s QR unattended model?

With this model, you won’t have to **create a specific payment order on Mercado Pago**. The order is generated by choosing a product or service and scanning the QR on the Point of Sale (POS).
We recommend this model for gas stations, vending machines and systems integrated with multiple wallets.

## Model features

The main characteristics are:

- Each Point of Sale has an associated URL to which Mercado Pago will ask if there is an order ready to pay.
- When a client scans the QR code in a Point of Sale, Mercado Pago sends a recurrent request to the URL associated on the POS. When order is ready, it will show the amount to pay in the client app. 
- Client will be able to pay only if there’s an order created for the scanned QR. 

> NOTE
> 
> Note
> 
> The URL should point to a service under your domain where you can display if there are pending orders for each Point of Sale of your store.

## Model flow

This is how the QR unattended model works:

>![Flujo de pago en punto de venta QR Mercado Pago](/images/qr-gas-station-flow.en.png)

1. Clients scan QR code from their app. 
2. Using the associated URL, Mercado Pago searches for the order in the merchant server.
3. (A) Point of sale informs status to the merchant server. <br/>
(B) If information is not available, merchant server will answer with a `HTTP 400`.<br/>
(C) Mercado Pago shows a waiting screen on the app.<br/>
(D) And searches again for the order in merchant server. 
4. (A) Point of sale sends order data to the merchant server.<br/> 
(B) When order is available, merchant server answers a  `HTTP 200` with the payment information needed to charge clients.
5. (A) Next, shows a payment screen on the client app. <br/>
(B) Merchant server receives an order notification.<br/>
(C) And confirms reception.
6. Finally, the client pays the order.
7. (A) The client sees a payment confirmation.<br/>
(B) Merchant server receives an order notification.<br/>
(C) And confirms reception.
8. (A) Merchant server consults order status with the received ID from the last notification to know if it’s closed or still pending.<br/>
(B) Mercado Pago returns respective data like status and payment information, among others. 
9. Once order is **closed**, receipt can be printed.

> NOTE
> 
> Note
> 
> On point 5, you’ll have to follow steps 8A and 8B to get order status.


### Next steps

<div>
<a href="https://www.mercadopago.com.ar/developers/en/guides/qr-code/qr-unattended/qr-unattended-part-b/" style="text-decoration:none;color:inherit">       
<blockquote class="next-step-card next-step-card-left">
<p class="card-note-title">How to integrate QR unattended model<span class="card-status-tag card-status-tag-required">REQUIRED</span></p>
<p>Learn how to set up this model step by step.</p>
</blockquote>
</div>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>