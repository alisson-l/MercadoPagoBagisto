<img width="100%" height="200" src="https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/fd56ca46-6384-4b7e-82bf-826850d1ea90" />
<p align="center" style="margin-top: 20px;">
<img loading="lazy" src="http://img.shields.io/static/v1?label=BAGISTO%20VERSION&message=2.0.0&color=WHITE&style=for-the-badge"/>
  <img loading="lazy" src="http://img.shields.io/static/v1?label=LAST%20UPDATE&message=2024-03-20&color=GREEN&style=for-the-badge"/>
   <img loading="lazy" src="http://img.shields.io/static/v1?label=CONTACT-ME&message=alisson.prof2@gmail.com&color=GREEN&style=for-the-badge"/>
</p>

<p>
  This package is based on paypal payment method of bagisto developed by: Alisson Lucas
  If u are interested in implement in your project just contact me: alisson.prof2@gmail.com
</p>

## Installation :arrow_forward:

After you already paid and get the package zipped sended by me. You need follow this steps.✔️

 1. First of all you need install de SDK from Oficial Mercado Pago Github. (https://github.com/mercadopago/sdk-php) or just run in your terminal
  
  ```
  composer require "mercadopago/dx-php:3.0.4"
  ```

 2. Take the package zipped and unpack in: packages/Webkul <br>
<p align="center" style="margin-top: 20px;">
    <img width="250" height="200" src="https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/4b8ebca6-60b7-4144-bfe8-fa239ac63696" />
</p>


 3. Add the package namespace to the psr-4 section in the composer.json file located in the root directory of your Bagisto application. Update it as follows:
  ![image](https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/bc26d002-6e6d-4746-8fe5-5b424816d81c)

 4. Register the package service provider in the config/app.php file located in the root directory of your Bagisto application. Add the following line to the providers array:
![image](https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/c517f434-99f7-46fa-8a5c-9c0084f48529)

5. Now you need add the following code into this two files:
   - packages/Webkul/Shop/src/Resources/views/checkout/onepage/summary.blade.php (BELOW PAYPAL METHOD)
     ![image](https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/9fe70aea-2342-4b92-bd3f-70ca351a991d)

     ```
     <div v-if="selectedPaymentMethod?.method == 'mercadopago'">
          {!! view_render_event('bagisto.shop.checkout.onepage.summary.mercadopago-smart-button.before') !!}

            <v-mercadopago-smart-button></v-mercadopago-smart-button>

          {!! view_render_event('bagisto.shop.checkout.onepage.summary.mercadopago-smart-button.after') !!}
      </div>
     ```
   - packages/Webkul/Checkout/src/Cart.php
     ![image](https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/c3ac078c-e430-4994-9c1b-8849600f1028)
      ```
      if ($finalData['payment']['method'] === 'mercadopago') {
        $finalData['payment']['additional'] = request()->get('orderData');
      }
     ```
 6. Now just run:
    ```
      composer dump-autoload
      php artisan optimize:clear
    ```  
 7. Finally in your admin panel will show the configs:
    ![image](https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/e8b54c00-83ab-407a-9ef3-4d71c615357e)
    ![image](https://github.com/alisson-l/MercadoPagoBagisto/assets/65234789/a6691d85-2990-40b7-9431-1196f4711512)


## Get access tokens in Mercado Pago 🔑

https://www.mercadopago.com.br/developers/pt/docs/your-integrations/credentials

   



