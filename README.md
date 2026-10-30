# OVAA Patched - Reverse Engineering Lab

This repository contains the reverse-engineered, modified, and re-signed version of the **Oversecured Vulnerable Android App (OVAA)** performed as part of mobile application security coursework[cite: 1].

## 🛠️ Summary of Changes & Hardening Performed
* **App Branding:** Updated the application name in `res/values/strings.xml` to **"OVA Patched by Shumaila"**.
* **Attack Surface Audit:** Modified `WebViewActivity`'s `android:exported` attribute from `"false"` to `"true"` in `AndroidManifest.xml`.
* **Hardcoded URLs Remediation:** Replaced sensitive hardcoded URLs and default login strings in `strings.xml` with placeholder values.
* **Manifest Hardening:** 
  * Changed `android:allowBackup` from `"true"` to `"false"` to prevent ADB backup extraction.
  * Changed `android:debuggable` from `"true"` to `"false"` to block runtime debugger attachments.
* **Recompilation & Signing:** Rebuilt the project using `apktool`, generated a custom 2048-bit RSA keystore via Java `keytool`, and successfully signed/verified the final artifact using `apksigner`[cite: 1].

## 📦 Deliverables
* **`ovaa_patched.apk`**: The final modified and re-signed Android application.
