# shopping-cart-PrestaShop
PrestaShop

=================================================
Plug 'n Pay - API Method
Payment Module for PrestaShop v1.5.x & v1.6.x
=================================================

***** IMPORTANT NOTES *****
This module is being provided "AS IS".  Limited technical support assistance will
be given to help diagnose/address problems with this module.  The amount of support
provided is up to PlugnPay's staff.

It is recommended if you experience a problem with this module, first seek assistance
through this module's readme file, then check with the PrestaShop community at
'www.prestashop.com', and if you are still unable to resolve the issue, contact us
via PlugnPay's Online Helpdesk.

This module requires your server to have SSL abilities & CURL.  PrestaShop will ask the
customer for all of their credit card info on your server's SSL secured billing pages.
The authorization will be done via PlugnPay's API payment method.  The cart itself will
store the customer's orders.  This module is for processing the authorization only.

If you want to change the behavior of this module, please feel free to make changes
to the files yourself.  However, customized PrestaShop modules will not be provided
support assistance.

In addition, you must have the 'Use SSL' option enabled in your PrestaShop shopping 
cart's General Preferences section, to properly use this module for checkout.
***************************

Installation:

For a default PrestaShop installation, simply upload the provided files into
your PrestaShop admin area normally & then enable/configure the the module normally.

For a custom PrestaShop installations, please refer to PrestaShop's online documentation
for how to manually install a module.
(http://doc.prestashop.com/display/PS14/Managing+Modules#ManagingModules-Installingmodules)


USAGE NOTES:

1 - This is a bare bones API payment module, so PnP is only send minimal data at time of
authorization.  The cart pretty much tracks all of the details itself.

2 - When configuring the payment module, the client is only asked to enter their PnP username,
[optionally a remote client password], and to select the card types allowed.  Everything else
is either hard coded within the module or is handled directly by the cart/gateway itself.

3 - Once the module is configured/active, the API payment option will only appear at time of
checkout when PrestaShop is setup to use HTTPS:// based URLs.  You must activate the 'Enable SSL'
option within PrestaShop's General Preferences section to enable this ability.

4 - On some servers, you may need to enable the 'register_globals' settings within your php.ini
file, in order for the 'parse_str' operation within the module to work correctly.


NOTE: The module assumes currency will be USD and only appears when the cart's currency matches.
If your cart is set to another currency, change the 3 character currency code that's hard coded
at the top of the 'hookPayment' function, within the module's 'plugnpayapi.php' script.

Also realize that this code itself is not very complex.  Practically every person that has
contacted us about errors found that some other code not associated with this contribution was
responsible, or because their CURL implementation was not properly set up or working.

Please do your own debugging before contacting anyone for assistance.

-----------------------------------------------------------------------------
Updates:

09/29/2013
- wrote new PrestaShop API module, specifically for PrestaShop build v1.5.0.17

03/17/2015
- minor adjustment to exp date year option, to support newer issued cards.

10/16/15
- removed hard coded cipher setting, so newer ciphers can be used with CURL.
- confirmed payment module compatibility with PrestaShop v1.6.x

10/20/15
- additional CURL adjustments
- cleaned up some code & images 
- fixed issue with some billing address & phone fields not being sent to gateway.

04/19/23
- adjusted format the card's exp date is sent to PnP
- added note to README about currency type matching requirement


