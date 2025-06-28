generates a TOTP (Time-based One-Time Password) and stores it in a Tosca buffer.
It's useful for test automation scenarios involving MFA/2FA logins using Microsoft or Google Authenticator-compatible codes.

✅ Features
🔐 Generates valid 6-digit TOTP

⚙️ Supports SHA1, SHA256, and SHA512 algorithms

🔄 Default encoding: Base32

🧠 Automatically sets OTP buffer for downstream Tosca steps

This solution is built with .Net 8 library(supported by latest versions of Tosca)

Otp.NET NuGet package is used for OTP generation

📦 Parameters (Tosca Test Step)
Name	Type	ActionMode	Required	Description
Secret	String	Buffer	✅ Yes	Base32-encoded shared secret
Algorithm	String	Buffer	❌ No	One of: sha1 (default), sha256, sha512
Encoding	String	Buffer	❌ No	Only base32 is supported (default)

📤 Output
Sets a buffer named OTP with the generated 6-digit code.

🧪 Example
Tosca Test Step Example:

Parameter	Value	ActionMode
Secret	JBSWY3DPEHPK3PXP	Buffer
Algorithm	sha1	Buffer
Encoding	base32	Buffer

Output - a 6 digit OTP is stored in the Buffer named 'OTP'

