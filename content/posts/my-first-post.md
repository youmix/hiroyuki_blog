---
title: '2023年'
date: 2023-01-06T02:00:00.000Z
draft: false
---

ご購入後、お支払いメールアドレスへ[(AuthCode（オースコード）](https://help.onamae.com/answer/8581 "オースコード")を送信しますので、移管先のレジストラへ入力してください。

<br><br>
{{< rawhtml >}}
<div id="smart-button-container">
      <div style="text-align: center;">
        <div id="paypal-button-container"></div>
      </div>
    </div>
  <script src="https://www.paypal.com/sdk/js?client-id=sb&enable-funding=venmo&currency=JPY" data-sdk-integration-source="button-factory"></script>
  <script>
    function initPayPalButton() {
      paypal.Buttons({
        style: {
          shape: 'rect',
          color: 'gold',
          layout: 'vertical',
          label: 'paypal',
          
        },

        createOrder: function(data, actions) {
          return actions.order.create({
            purchase_units: [{"description":"\nhiroyuki.blogドメイン\n¥100,000","amount":{"currency_code":"JPY","value":100000}}]
          });
        },

        onApprove: function(data, actions) {
          return actions.order.capture().then(function(orderData) {
            
            // Full available details
            console.log('Capture result', orderData, JSON.stringify(orderData, null, 2));

            // Show a success message within this page, e.g.
            const element = document.getElementById('paypal-button-container');
            element.innerHTML = '';
            element.innerHTML = '<h3>Thank you for your payment!</h3>';

            // Or go to another URL:  actions.redirect('thank_you.html');
            
          });
        },

        onError: function(err) {
          console.log(err);
        }
      }).render('#paypal-button-container');
    }
    initPayPalButton();
  </script>
{{< /rawhtml >}}
<br><br>
※取引に問題があった場合は[PayPal問題解決センター](https://www.paypal.com/jp/brc/article/resolving-paypal-disputes "PayPal問題解決センター")で

<br><br>
※メールで[質問などはこちら](https://tayori.com/form/32a031e05185ff895af57ebc48d27d1aaecc22e0/ "メール")
