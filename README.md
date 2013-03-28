Magento Remove Dashboard Links
==============================

Remove unwanted links from Account Dashboard Navigation
--------

**Step 1:** GO TO ( YourTemplate/customer/account/navigation.phtml )


**Step 2:** :Replace This Line: *<?php $_count = count($_links); ?>*


#####With:
```php
<?php $_count = count($_links); /* Add or Remove Account Left Navigation Links Here -*/
    unset($_links['account']); /* Account Info */     
    unset($_links['account_edit']); /* Account Info */            
    unset($_links['tags']); /* My Tags */
    unset($_links['invitations']); /* My Invitations */
    unset($_links['reviews']);  /* Reviews */
    unset($_links['wishlist']); /* Wishlist */
    unset($_links['newsletter']); /* Newsletter */
    unset($_links['orders']); /* My Orders */
    unset($_links['address_book']); /* Address */
    unset($_links['enterprise_customerbalance']); /* Store Credit */
    unset($_links['OAuth Customer Tokens']); /* My Applications */
    unset($_links['enterprise_reward']); /* Reward Points */
    unset($_links['giftregistry']); /* Gift Registry */
    unset($_links['downloadable_products']); /* My Downloadable Products */
    unset($_links['recurring_profiles']); /* Recurring Profiles */
    unset($_links['billing_agreements']); /* Billing Agreements */
    unset($_links['enterprise_giftcardaccount']); /* Gift Card Link */
?> 
```

