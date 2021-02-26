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

> Please note that we can only offer support for the module itself. While every effort has been made to ensure the payment module is complete and bug free, we cannot guarantee normal functionality if unsupported changes are made.

# Rebranding

To rebrand this module, please complete the following steps:

1. In file `httpdocs/includes/languages/english/modules/payment/payment_network.php` change the following:
	- Line 9: `define('MODULE_PAYMENT_PAYMENT_NETWORK_DIRECT_URL','https://gateway.example.com/direct/');` change this URL to your gateway URL we supply
	- Line 10: `define('MODULE_PAYMENT_PAYMENT_NETWORK_MODAL_URL','https://gateway.example.com/hosted/modal');` change this URL to your gateway URL we supply
	- Line 11: `define('MODULE_PAYMENT_PAYMENT_NETWORK_FORM_URL', 'https://gateway.example.com/hosted/');` change this URL to your gateway URL we supply
	- Line 13: `define('MODULE_PAYMENT_PAYMENT_NETWORK_ADMIN_TITLE', 'Payment Network Integration');` changing Payment Network to your brand name
	- Line 14: `define('MODULE_PAYMENT_PAYMENT_NETWORK_ADMIN_DESCRIPTION', '<a target=\"_blank\" href=\"https://www.example.com?ref=zen-cart\"><img style=\"float:right;margin-right:8px;\" src=\"https://www.example.com/images/logo.png?ref=zen-cart\"/></a> <br/><a target="_blank" href="https://www.example.com/signup?ref=zen-cart">Click Here to Sign Up for an Account</a><br /><br /><a target="_blank" href="https://mms.example.com/admin?ref=zen-cart">Login to the PaymentNetwork Merchant Area</a><br /><br /><strong>Requirements:</strong><br /><hr />*<strong>PaymentNetwork Account</strong> (see link above to signup)<br />*<strong>PaymentNetwork MerchantID</strong> available from your Merchant Area<br/> *<strong>PaymentNetwork Merchant Password</strong> set in mms &amp; required for zen-cart');` changing references to www.example.com to your website URL and PaymentNetwork to your brand name
2. When downloading as a zip file, you can right-click and rename to remove the `Unbranded` text from the filename.

# Installing and configuring the module

1. Make sure that all files inside the httpdocs folder are inserted into the root directory of where Zen Cart is installed (including paymentnetwork_callback.php in the main folder)
2. Some installations will not require you to run the SQL files provided. However, strict database privileges on a server (specifically CREATE, DELETE and ALTER) will prevent the a full installation of this module. If this is the case, you will need to manually run the SQL into your site's database with CREATE, and ALTER privileges; making sure to allow DELETE access for paymentnetwork_temp_carts normal operation which will help keep the table clean and save space. Ensure that you enter your correct table name (my_table_name in the example below) in orders.sql
3. Mouseover the 'Modules' link in the top menu and click 'Payment'. Next, click the circle for PaymentNetwork Form and finally click 'install' on the right side of the screen
4. Follow the instructions that appear, and enter all the necessary details, such as the Merchant ID and signature. Click 'update', and PaymentNetwork is now integrated with your shopping cart

If you would like to make edits to the PaymentNetwork Integration such as updating the Merchant ID, hover over the modules drop down menu and click payments. Click on PaymentNetwork Integration in the list that appears, and click on edit on the right hand side

License
----
MIT
