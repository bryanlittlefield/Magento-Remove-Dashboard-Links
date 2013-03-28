Magento Remove Dashboard Links
==============================

Remove unwanted links from Account Dashboard Navigation

####GO TO: YourTemplate/customer/account/navigation.phtml
-----------------------------------------------------

####Replace This Line: <?php $_count = count($_links); ?>
-----------------------------------------------------

#### With:
```php
<?php
/**
 * Magento
 *
 * NOTICE OF LICENSE
 *
 * This source file is subject to the Academic Free License (AFL 3.0)
 * that is bundled with this package in the file LICENSE_AFL.txt.
 * It is also available through the world-wide-web at this URL:
 * http://opensource.org/licenses/afl-3.0.php
 * If you did not receive a copy of the license and are unable to
 * obtain it through the world-wide-web, please send an email
 * to license@magentocommerce.com so we can send you a copy immediately.
 *
 * DISCLAIMER
 *
 * Do not edit or add to this file if you wish to upgrade Magento to newer
 * versions in the future. If you wish to customize Magento for your
 * needs please refer to http://www.magentocommerce.com for more information.
 *
 * @category    design
 * @package     base_default
 * @copyright   Copyright (c) 2012 Magento Inc. (http://www.magentocommerce.com)
 * @license     http://opensource.org/licenses/afl-3.0.php  Academic Free License (AFL 3.0)
 */
?>
<div class="block block-account">
    <div class="block-title">
        <strong><span><?php echo $this->__('My Account'); ?></span></strong>
    </div>
    <div class="block-content">
        <ul>
            <?php $_links = $this->getLinks(); ?>
            <?php $_index = 1; ?>
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
            <?php foreach ($_links as $_link): ?>
                <?php $_last = ($_index++ >= $_count); ?>
                <?php if ($this->isActive($_link)): ?>
                    <li class="current<?php echo ($_last ? ' last' : '') ?>"><strong><?php echo $_link->getLabel() ?></strong></li>
                <?php else: ?>
                    <li<?php echo ($_last ? ' class="last"' : '') ?>><a href="<?php echo $_link->getUrl() ?>"><?php echo $_link->getLabel() ?></a></li>
                <?php endif; ?>
            <?php endforeach; ?>
        </ul>
    </div>
</div>
```

