Devnora Tv - Android Box / TV APK banane ka tareeqa
===================================================

1) Computer par Android Studio install karein (free): developer.android.com/studio
2) Android Studio kholein > "Open" > is DevnoraTv folder ko chunein (jis mein settings.gradle hai).
3) Pehli baar "Gradle sync" ho jayega (internet chahiye, thoda time lagta hai). Jo update/SDK mange, Accept/Install kar dein.
4) Menu: Build > Build Bundle(s) / APK(s) > Build APK(s)
5) Kaam hone par neeche "locate" ka link aata hai. File yahan milti hai:
      app/build/outputs/apk/debug/app-debug.apk
6) Is apk ko USB pen drive mein copy karein, box mein lagayein, box ke file manager se apk kholein aur Install dabayein.
   (Box ki Settings mein "Unknown sources / Install unknown apps" allow karna padega.)
   Ya ADB se:  adb connect BOX_IP   phir   adb install app-debug.apk

Zaruri baatein
--------------
* App aapki GitHub Pages site (https://newlook9.github.io/dntv/) kholti hai. Site update karein to app khud update ho jati hai.
  Link badalna ho to app/src/main/java/com/devnora/tv/MainActivity.java mein APP_URL badal dein.
* Chalne ke liye internet zaruri hai.
* Agar Android Studio gradle wrapper par shikayat kare: File > New > New Project > "Empty Views Activity" banayein
  (Package: com.devnora.tv, Language: Java, Minimum SDK 21), phir is folder ki ye files us project mein copy kar dein:
  AndroidManifest.xml, MainActivity.java, aur res folder (mipmap-* aur drawable/banner.png). Phir wahi Build APK.
* Remote: tir wale buttons se chalein, OK dabane se channel chalta hai, Back se wapas. Remote ke Channel +/- se agla/pichla channel.

ONLINE APK BANANA (Android Studio ke baghair) - GitHub Actions
--------------------------------------------------------------
1) github.com par naya repository banayein (Public, naam: devnora-tv-apk).
2) Is DevnoraTv folder ke andar ki saari files aur folders (app, gradle, settings.gradle, build.gradle ...) us repository ke root mein upload karein.
   (Computer ke browser mein folder drag & drop ho jata hai.)
3) Agar .github folder upload na ho: repository mein "Add file > Create new file" dabayein, naam mein likhein:
      .github/workflows/build.yml
   aur is folder wali build.yml ka poora matn paste karke Commit karein.
4) Upar "Actions" tab kholein > "Build APK" > "Run workflow" dabayein. 3-6 minute intezar karein.
5) Hari tick aane par us run par click karein. Neeche "Artifacts" mein Devnora-Tv-apk milega. Download karke zip kholein, andar app-debug.apk hai.
