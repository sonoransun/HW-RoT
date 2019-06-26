# Web Technology Tutorial with Hardware Root of Trust

This tutorial will demonstrate how to deploy web technologies backed by a hardware root of trust using macOS for development. For personal identification and secret storage we will use the YubiKey 5 device. In the cloud, secrets will be protected by the Amazon Web Services Key Management Service (AWS KMS).

## Background

A hardware root of trust is a highly reliable hardware, firmware, and software component that performs a limited set of critical security functions.  By designing such a system as a hardened physical package with minimal software and interfaces, the attack surface is greatly reduced.

While not infallible, these systems provide defense in depth. Compromise of a traditional computing environment exposes all of the secrets in use, while a hardware root of trust keeps those secrets intact. In addition, auditing and access controls allow recovery post-breach with less effort and key rotation, while providing clarity on the scope of damage involved.

## Agenda

This tutorial is split into distinct topics. If you already have the prerequisites covered, feel free to skip ahead to the appropriate section.

The topics included are:

- [YubuKey authentication on macOS.](webtech-macos-yubikey.md)
- GNU Privacy Guard signing and encryption with YubiKey.
- OpenSSH authentication with YubiKey.
- Amazon Web Services authentication with YubiKey.
- Provisioning AWS Key Management Service.
- KMS wrapping and unwrapping of secret data.
- Secret Fortune demonstration using hardware root of trust.
- [Frequently Asked Questions.](webtech-faq.md)

---

### References:

- [YubiKey 5 Series](https://www.yubico.com/products/yubikey-5-overview/)
- [AWS KMS](https://aws.amazon.com/kms/features/)
