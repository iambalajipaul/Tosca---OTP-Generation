This solution generates a TOTP (Time-based One-Time Password) and stores it in a Tosca buffer.
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
Secret	String	Input	✅ Yes	Base32-encoded shared secret
Algorithm	String	Input	❌ No	One of: sha1 (default), sha256, sha512
Encoding	String	Input	❌ No	Only base32 is supported (default)

📤 Output
Sets a buffer named OTP with the generated 6-digit code.

🧪 Example
Tosca Test Step Example:

Parameter	Value	ActionMode
Secret	JBSWY3DPEHPK3PXP	Input


Output - a 6 digit OTP is stored in the Buffer named 'OTP' //Note - For trial module, you can only see the TOTP in Loginfo.

Steps to implement:
1. Copy the files GenerateTOTP.dll and Otp.NET.dll to TBox home folder(Usually C:\Program Files (x86)\TRICENTIS\Tosca Testsuite\TBox)(Note: Tosca should be opened after pasting the files as these files are loaded during opening)
2. Open Tosca commander and your project.
3. Import the module Totp generation_Trial.tsu file in your Tosca project
4. Add the module generate OTP to your test case and provide secret to generate the OTP
5. In the step where you need to insert the value in UI, use B{OTP}

Steps to get secret(Microsoft Accounts):
1. Navigate to https://mysignins.microsoft.com/security-info -> signIn
2. Add sign-in method -> Select Microsoft Authenticator -> Select 'I want to use a different Authenticator app' -> Click Next -> Select Can't scan image to get the secret key

If you want further customization or any querires, feel free to reach out to me via https://www.linkedin.com/in/contactbalaji/

