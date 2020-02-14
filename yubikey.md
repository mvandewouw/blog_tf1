## A little background on SFA/2FA/MFA
What is 2FA(Two factor authentication)/MFA(Multi factor authentication)? According to [wikipedia](https://en.wikipedia.org/wiki/Multi-factor_authentication):
1) Something the user knows (and only the user knows)
2) Something the user has (and only the user has)
3) Something the user is (and only the user is)

So for example 1) could be a password and 2) could be an security token and 3) could be a fingerprint or retina scan or something.

2FA is a basicly a subset of the above.

The absolute worst you can have is a SFA (Single factor authentication). Your account could be vulnerable to a number of attacks. Brute forcing / dictionary checking is one of them. A lot of people still use an easy, dictionary based password that also is used for different services as well. I will not go into detail on this problem but it happens. A lot.

There are all kinds of 2FA availabe. The most known 2FA are:
1) SMS token
2) Authenticator app (approval based sign in or OTP (one time password))
3) Security token

A list of pro's and con's can be found [here](https://www.scentropic.com/blog/2018/aug/google-2fa/google-2fa.shtml)

Basicly the security token is the most secure option here. There are also lots of tokens available on the market. Google has the [titan security key](https://cloud.google.com/titan-security-key/). Or the [onlykey](https://onlykey.io/). 
I focussed myself on the yubikey. 

I have the following devices to play with:
1) [YubiKey C Nano FIPS](https://www.yubico.com/product/yubikey-c-nano-fips) (usb-c form factor)

![YubiKey C Nano FIPS](https://media.yubico.com/media/catalog/product//c/f/cfips-nano-back.png "YubiKey C Nano FIPS")

2) [YubiKey 5 Nano](https://www.yubico.com/product/yubikey-5-nano) (usb-a form factor) 

![YubiKey C Nano FIPS](https://media.yubico.com/media/catalog/product//y/u/yubikey-5-nano_2.png "YubiKey C Nano FIPS")

3) [YubiKey 5 NFC](https://www.yubico.com/product/yubikey-5-nfc) (usb-a form factor)

![YubiKey C Nano FIPS](https://media.yubico.com/media/catalog/product//y/u/yubikey-5-nfc_3.png "YubiKey C Nano FIPS")


I do have a Yubikey 4 fips and 2 yubikey 5 (the nfc and small form factor)
https://datalocker.com/fips-140-2-levels-explained/




## Yubikey 2fa

Over the past couple of months i started using yubikeys for hardening my online posture and incorporate 2fa with every service possible.
Also using it to store my gpg keys andd sign my commits and use the hardened ssh-agent.
Questions may rise for example, why not an authenticator app, or sms based 2fa? Simply because it is less secure.
It might be good for services online that are of lesser importance, but when it is about mail take no consessions. Be secure as you can get.
Simply because the mail is the root of your identity online. When this account is compromised password resets can be done for a lot of services you registered for.






The first thing i did was verify the genuitiy of my yubikeys

https://www.yubico.com/genuine/





https://www.scentropic.com/blog/2018/aug/google-2fa/google-2fa.shtml
https://hackernoon.com/use-a-yubikey-as-a-mfa-device-to-replace-google-authenticator-b4f4c0215f2



b86d79359dfd033273360adfd5553792e2719a2d


password manager keepassxc install as snap on ubuntu, dont forget to run:
sudo snap connect keepassxc:raw-usb core:raw-usb


Yubikey manager: Applications>OTP>Long touch (slot2)
keepassxc: Database>Change Master key>Add additional protection>


953da066dff197eb627b09231f18b03208a48179

## Installation of yubikey-manager
<code>
sudo apt-add-repository ppa:yubico/stable
sudo apt update
sudo apt install yubikey-manager-qt
</code>
With the yubikey-manager you can configure your yubikey. It also comes with the cli ykman tool which you can use as well.
Example options ykman:

### List yubikeys:
<code>
ykman list
</code>

### Info about your yubikey:
<code>
ykman info
</code>
When multiple yubikeys inserted you have to use the --device flag
<code>
ykman --device 1234 info
</code>


https://gist.github.com/artizirk/d09ce3570021b0f65469cb450bee5e29

https://blog.tinned-software.net/create-gnupg-key-with-sub-keys-to-sign-encrypt-authenticate/

https://github.com/drduh/YubiKey-Guide


sub (subkey)
uid ()

https://sectigostore.com/blog/what-is-multi-factor-authentication-and-how-does-it-differ-from-2fa-sfa/  