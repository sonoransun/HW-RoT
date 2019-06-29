# Gnu Privacy Guard Signing and Encryption with YubiKey

GNU Privacy Guard supports authentication and key storage via YubiKey.  We will create a new master key and subkeys for GPG which will be used for SSH authentication, signing, and encryption. Once generated, these keys will be imported into the YubiKey for protection.

## Preparing a macOS Ephemeral Disk Volume

The keys we generate must not be persisted after import into the YubiKey. To ensure that temporary storage we use during key generation is securely erased, an ephemeral disk volume backed by AES encryption is used. Once we are finished with this volume, we can erase it and forget the passphrase.

Create an ephemeral volume **CryptStorage** on file backed disk volume **EphemeralStorage.dmg** as follows:

- Open Finder Applications, open the Utilities folder, and then click to launch the Disk Utility application.
- Choose File from top menu, then New, then Disk Image.
- In the new image modal window, perform the following:
- Enter the name **EphemeralStorage** in the **Save As** entry.
- Enter the name **CryptStorage** in the **Name** entry. This is what the volume will be mounted as.
- In the **Encryption** drop down menu, select **AES-128** or **AES-256**. You will be prompted for a passphrase. Choose a random diceware passphrase that you forget once used.
- **IMPORTANT!** When setting the passphrase, un-select the option **Remember password (add to keychain)**. Otherwise, you must manually remove this entry from Keychain later.
- Click the **Create** button.

### Launch Disk Utility application

The Disk Utility application is used to create an ephemeral encrypted volume. Keys generated for this tutorial and stored on the ephemeral volume can be safely forgotten once that volume is deleted.

[![Create new disk volume](/img/disk-utility-new.png "Create new disk volume")](/img/disk-utility-new-disk.png)

### Configure new volume details

[![Configure new disk volume details](/img//home/user/Documents/img-webtech-sshots/disk-utility-ephemeral-disk-setup.png "Configure new volume details")](/img//home/user/Documents/img-webtech-sshots/disk-utility-ephemeral-disk-setup.png)

### Configure random ephemeral password

[![Configure random ephemeral password](/img/disk-utility-ephemeral-disk-password.png "Configure random ephemeral password")](/img/disk-utility-ephemeral-disk-password.png)

### Set new disk image path

[![Set new disk image path](/img/disk-utility-ephemeral-disk-image-path.png "Set new disk image path")](/img/disk-utility-ephemeral-disk-image-path.png)

### Create ephemeral volume

[![Create ephemeral volume](/img/disk-utility-ephemeral-disk-create.png "Create ephemeral volume")](/img/disk-utility-ephemeral-disk-create.png)

### Verify mounted volume

[![Verify mounted volume](/img/disk-utility-ephemeral-disk-mounted.png "Verify mounted volume")](/img/disk-utility-ephemeral-disk-mounted.png)


## Create the GPG Master Key

First we create the master key.

---

### References:

- [Dice-Generated Passphrases](https://www.eff.org/dice)
- [Using Your YubiKey with OpenPGP](https://support.yubico.com/support/solutions/articles/15000006420-using-your-yubikey-with-openpgp)
