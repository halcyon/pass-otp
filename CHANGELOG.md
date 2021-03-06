Change Log
=============

Version 1.0.0 *(2017-03-20)*
-------------------------------

 * New: `insert` command accepts `otpauth://` URIs directly.
 * New: `append` command appends or replaces OTP URIs in existing passfiles.
 * New: `validate` command validates an `otpauth://` URI against the
   [Key Uri Format](https://github.com/google/google-authenticator/wiki/Key-Uri-Format) standard.
 * Rename `show` to `code` for disambiguation from `pass show`. `show` is still
   supported as an alias.

 * **Drop `insert totp` and `insert hotp` commands.** These were cumbersome to
   support and are obviated by key URIs.

 * **Drop support for the 0.1.0 OTP passfile format.** Please see the
   [Migrating from pass-otp 0.1.0](https://github.com/tadfisher/pass-otp/blob/v1.0.0/README.md#migrating-from-pass-otp-01)
   section of the README for advice on migrating your OTP passfiles from the
   previous version.

 * **Drop support for entering OTP secrets as arguments.** This practice is
   prone to history leakage, which is why it is not supported by `pass insert`.
   Intrepid users may use `echo <uri> | pass otp insert`, but they should be
   warned to disable their shell's history feature.

Version 0.1.0 *(2017-02-14)*
----------------------------

 * Initial release.
 * Supports the following commands:
   - `insert totp`: Insert a TOTP secret.
   - `insert hotp`: Insert an HOTP secret.
   - `show`: Generate a QR code.
   - `uri`: Generate an otpauth:// URI for a secret.
