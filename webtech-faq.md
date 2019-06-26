# Frequently Asked Questions

### 2nd Factor Authentication (2FA)

Q: I already use a second factor authentication mechanism, like SMS code confirmation, when logging into accounts. Isn't this sufficient?

A: Unfortunately, not all second factor authentication methods are equal, and some lack the robustness of a hardware root of trust. For example, SMS verification codes as a second factor for online accounts have been discouraged since 2016 due to inherent vulnerabilities of the global telecommunications network.

---

### Require YubiKey for Authentication

Q: Is it possible to require the YubiKey to authenticate accounts? (For example, to force disable password authentication once the YubiKey has been configured.)

A: While this is technically possible, it is also outside the scope of this tutorial and carries additional key recovery and management overhead.

---

### Using Multiple YubiKeys

Q: Can I use multiple YubiKeys at the same time?

A: Using multiple YubiKeys concurrently is problematic due to the way some of the software in this tutorial handles session establishment and lifecycle. While technically possible, it is outside the scope of this tutorial. See the discussion, ["Using two yubikeys not covered under guide"](https://github.com/drduh/YubiKey-Guide/issues/19), for additional context.

---

### Third Party Hardware

Q: The YubiKey stored my keys securely. Does this mean I can use a sketchy kiosk at the hotel to login to my accounts without risk?

A: Yes, the YubiKey keeps your secret keys secret. However, an established session on a compromised machine is still a session under the attacker's control, just as if they had stolen your authentication credentials (for the duration of the session).  Thus you should never use hardware you don't trust, no matter the security of the keys used.

---

### Key Recovery and Backups

Q: Is is possible to backup the keys on a YubiKey in such a way that I can restore them on a replacement device if I lose the first one?

A: Proper key backup and recovery is a complicated subject outside the scope of this tutorial. In practice, there are recovery passphrases, M of N quorums, and envelope encryption configurations which can achieve the resliency and recovery desired without compromising the security of the keys you are trying to protect. An important aspect of these schemes is physical security, where controlled access, like a safe deposit box, are used to protect secrets used for key recovery.

---

### Password Managers

Q: I would like to use a password manager application to store distinct randomly generated website passwords and other authentication information. Can I use the YubiKey as a password manager?

A: Using a password manager with YubiKey is outside the scope of this tutorial. In such a setup, you would open or authenticate with the password manager application using the YubiKey, however, the passwords would be stored by the manager application and not on the YubiKey device itself. See the [pwSafe on macOS instructions](https://www.yubico.com/why-yubico/for-individuals/password-managers/pwsafe/) for more information.

---

### References:

- [NIST Recommends SMS Two-Factor Authentication Deprecation](https://threatpost.com/nist-recommends-sms-two-factor-authentication-deprecation/119507/)
- [Getting 2FA Right in 2019](https://blog.trailofbits.com/2019/06/20/getting-2fa-right-in-2019/)
- [Backup GPG keys on encrypted USB](https://github.com/drduh/YubiKey-Guide#backup)
- [Configure macOS for smart card-only authentication](https://support.apple.com/en-us/HT208372)

