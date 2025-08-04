## ✅ How to Sign an APK on Arch Linux (with Android Studio & apksigner)

This guide will walk you through signing an unsigned APK using a `.jks` keystore, so you can publish or distribute your app.

---

### 🛠️ Step 1: Install Android Studio

Use `yay` or any AUR helper:

```bash
yay -S android-studio
```

This will also install Android SDK and build tools required for signing your APK.

---

### 🗝️ Step 2: Generate a Keystore (.jks)

1. Open **Android Studio**
2. Go to:
   **Build > Generate Signed Bundle / APK**
3. Select **APK**, click **Next**
4. Click **Create new\...** next to the *Key store path* field
5. Fill in the fields:

   * **Key store path:** e.g. `~/passme/key.jks`
   * **Key alias:** e.g. `key0`
   * **Passwords:** Choose and remember your keystore and key password (can be the same)
6. Finish the wizard to generate your keystore and save it in a known location

📌 **Important:** Save your `.jks`, alias, and passwords somewhere safe. You’ll need them every time you want to sign an APK.

---

### 📦 Step 3: Prepare Your APK for Signing

Make sure your apk file has no spaces in the name:

```bash
mv 'app-universal-release-unsigned (copy).apk' unsigned.apk
```

---

### 🔏 Step 4: Sign the APK with `apksigner`

```bash
~/Android/Sdk/build-tools/36.0.0/apksigner sign \
  --ks ~/passme/key.jks \
  --ks-key-alias key0 \
  --ks-pass pass:pljs2001 \
  --key-pass pass:pljs2001 \
  --out signed_app.apk \
  unsigned.apk
```


🔐 **Note:** Using `--ks-pass pass:...` is okay for local development but not secure for production scripts. You can omit it and get prompted safely.

---

### ✅ Step 6: Verify the Signed APK

```bash
~/Android/Sdk/build-tools/36.0.0/apksigner verify --verbose --print-certs signed_app.apk
```

Expected output:

```
Verifies
Verified using v1 scheme (JAR signing): true
Verified using v2 scheme (APK Signature Scheme v2): true
...
Signer #1 certificate DN: CN=Your Name, ...
```

If you see `DOES NOT VERIFY`, the APK is either unsigned or incorrectly signed.

---

### ✅ You're Done!

You now have a properly signed APK (`signed_app.apk`) ready to install on devices or upload to the Play Store.
