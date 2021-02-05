# README

# Contents

- Introduction
- Prerequisites
- Rebranding
- Installing and configuring the module
- License

# Introduction

This Zencart module provides an easy method to integrate with the payment gateway.
 - The httpdocs directory contains the files that need to be uploaded to the root directory of where Zencart is installed
 - Supports Zencart versions: **1.5.x**

# Prerequisites

- The module requires the following prerequisites to be met in order to function correctly:
    - For a full list of requirements please see: https://docs.zen-cart.com/user/first_steps/server_requirements/
    - SSL **NB: HTTPS is expected to be in place as the payment gateway will respond over SSL when integrating directly. Failure to provide an environment where HTTPS traffic is possible, will result in the 3DSv2 payment flow failing***

> Please note that we can only offer support for the Module itself. While every effort has been made to ensure the payment module is complete and bug free, we cannot guarentee normal functionality if unsupported changes are made.

# Rebranding

To rebrand this module, please complete the following steps:

1. In file `httpdocs/includes/languages/english/modules/payment/payment_network.php` change the following:
	- Line 9: `define('MODULE_PAYMENT_PAYMENT_NETWORK_DIRECT_URL','https://gateway.example.com/direct/');` changing gateway.example.com to your gateway url
	- Line 10: `define('MODULE_PAYMENT_PAYMENT_NETWORK_MODAL_URL','https://gateway.example.com/hosted/modal');` changing gateway.example.com to your gateway url
	- Line 11: `define('MODULE_PAYMENT_PAYMENT_NETWORK_FORM_URL', 'https://gateway.example.com/hosted/');` changing gateway.example.com to your gateway url
	- Line 13: `define('MODULE_PAYMENT_PAYMENT_NETWORK_ADMIN_TITLE', 'Payment Network Integration');` changing Payment Network to your brand name
	- Line 14: `define('MODULE_PAYMENT_PAYMENT_NETWORK_ADMIN_DESCRIPTION', '<a target=\"_blank\" href=\"https://www.example.com?ref=zen-cart\"><img style=\"float:right;margin-right:8px;\" src=\"https://www.example.com/images/logo.png?ref=zen-cart\"/></a> <br/><a target="_blank" href="https://www.cardstream.com/signup?ref=zen-cart">Click Here to Sign Up for an Account</a><br /><br /><a target="_blank" href="https://mms.cardstream.com/admin?ref=zen-cart">Login to the PaymentNetwork Merchant Area</a><br /><br /><strong>Requirements:</strong><br /><hr />*<strong>PaymentNetwork Account</strong> (see link above to signup)<br />*<strong>PaymentNetwork MerchantID</strong> available from your Merchant Area<br/> *<strong>PaymentNetwork Merchant Password</strong> set in mms &amp; required for zen-cart');` changing references to www.example.com to your website url and PaymentNetwork to your brand name

# Installing and configuring the module

1. Make sure that all files inside the httpdocs folder are inserted into the root directory of where Zen Cart is installed (including cardstream_callback.php in the main folder).
2. Some installations will not require you to run the SQL files provided. However, strict database privileges on a server (specifically CREATE, DELETE and ALTER) will prevent the a full installation of this module. If this is the case, you will need to manually run the SQL into your site's database with CREATE, and ALTER priveledges; making sure to allow DELETE access for cardstream_temp_carts normal operation which will help keep the table clean and save space. Ensure that you enter your correct table name (my_table_name in the example below) in orders.sql

```
ALTER TABLE my_table_name ADD COLUMN `cardstream_xref` VARCHAR(128) NULL, ADD COLUMN `cardstream_transactionUnique` VARCHAR(128) NULL, ADD COLUMN
`cardstream_amount_received` FLOAT NOT NULL DEFAULT '0.0', ADD COLUMN `cardstream_authorisationCode` VARCHAR(128) NULL, ADD COLUMN `cardstream_responseMessage`
TEXT NULL, ADD COLUMN `cardstream_lastAction` VARCHAR(32) NULL
```

3. Mouseover the Modules link in the top menu and click Payment. Next, click the circle for CardStream Form and finally click install on the right side of the screen.
4. Follow the instructions that appear, and enter all the necessary details, such as the Merchant ID and signature. Click update, and Cardstream is now integrated with your shopping cart.

If you would like to make edits to the Cardstream Integration such as updating the Merchant ID, hover over the modules drop down menu and click payments. Click on Cardstream Integration in the list that appears, and click on edit on the right hand side.

License
----
MIT
