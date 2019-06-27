# YubiKey Authentication on macOS

Apple's flagship operating system, macOS, supports authentication via hardware root of trust using the Personal Identity Verification capabilities of the OS.  This is commonly referred to as SmartCard authentication, however, the YubiKey can also function as a PIV device, just like a SmartCard.

## Setting up your YubiKey 5 device

### Installing YubiKey Manager

Configuration of your YubiKey 5 device requires a software application called YubiKey Manager.
 You can obtain this software from the [YubiKey Manager Downloads](https://www.yubico.com/products/services-software/download/yubikey-manager/) page.

### Disable unnecessary interfaces

Launch the YubiKey Manager application to configure enabled interfaces on the YubiKey.
 Disable all of the NFC interfaces, as this tutorial only requires USB device access.

[![Configure enabled YubiKey interfaces](/img/yubikey-interfaces.png "Configure enabled YubiKey interfaces")](/img/yubikey-interfaces.png)

### Set new YubiKey PIN, PUK, and Key

When changing the PIN, PUK, and Key for the YubiKey device, you can select the "Use default" option instead of manually specifying the factory default values.

[![Configure YubiKey PINs](/img/yubikey-configure-pins.png "Configure YubiKey PINs")](/img/yubikey-configure-pins.png)

The new PIN must be six digits long.

[![Set PIN](/img/yubikey-set-pin.png "Set PIN")](/img/yubikey-set-pin.png)

The new PUK must be eight digits long.

[![Set PUK](/img/yubikey-set-puk.png "Set PUK")](/img/yubikey-set-puk.png)

Use the "Generate" option to create a new random key. Do not try to use a memorable key value.

[![Set key](/img/yubikey-set-key.png "Set key")](/img/yubikey-set-key.png)

### Confirm PINs and Key are updated

Verify that PINs have been set, and that the new Key is protected by PIN.

[![PINs configured](/img/yubikey-post-configure-pins.png "PINs configured")](/img/yubikey-post-configure-pins.png)

### Configure macOS PIV authentication

Pairing this new YubiKey device with macOs requires entering the PIN and Keychain password.

[![Enter pairing PIN](/img/yubikey-pairing-pin.png "Enter pairing PIN")](/img/yubikey-pairing-pin.png)

[![Enter KeyChain password](/img/yubikey-pairing-keychain.png "Enter KeyChain password")](/img/yubikey-pairing-keychain.png)

### Login via YubiKey

Log out, then insert the YubiKey device to authenticate via PIV and PIN.
 You should observe the authentication prompt adjust to PIN entry once the YubiKey has been inserted.

---

### References:

- [Using Your YubiKey as a Smart Card in macOS](https://support.yubico.com/support/solutions/articles/15000006468)
