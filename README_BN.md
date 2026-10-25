# GTS Tarek Aim Guide — Android Source Project

এই ZIP-এ Android Studio/Gradle দিয়ে APK বানানোর জন্য Android প্রজেক্ট, আপনার দেওয়া GTS Tarek লোগো, অ্যাপের পাসওয়ার্ড এবং Telegram/Game লিংক যুক্ত করা হয়েছে।

## অ্যাপের মধ্যে যা আছে
- GTS Tarek লোগো ও নাম
- Play বাটনে পাসওয়ার্ড চাইবে: `GTSTAREK141`
- Carrom Pool ইনস্টল থাকলে সেটি চালু করার চেষ্টা করবে; না থাকলে Play Store পেজ খুলবে
- Telegram চ্যানেল: https://t.me/gtstarek
- Floating manual aim-line overlay
- Experimental screen-capture/detection mode

## APK বানানোর সহজতর পথ: GitHub Actions (ফোন থেকেও করা যায়)
1. ZIP-টি Extract করুন।
2. GitHub-এ একটি নতুন repository তৈরি করুন এবং এই ফোল্ডারের সব ফাইল upload করুন (root-এ `app`, `build.gradle`, `settings.gradle`, `.github` থাকতে হবে)।
3. Repository-এর **Actions** ট্যাব খুলুন। `Build Android APK` workflow থাকলে সেটি খুলে **Run workflow** চাপুন। প্রথমবার workflow না দেখালে `Actions` enable করুন বা একটি commit করুন।
4. Build শেষ হলে ওই workflow run-এর নিচে **Artifacts** অংশে `GTS-Tarek-Aim-Guide-debug-apk` ডাউনলোড করুন। ZIP extract করে `app-debug.apk` ফোনে ইনস্টল করুন। Android চাইলে “Install unknown apps” অনুমতি দিতে হবে।

## গুরুত্বপূর্ণ সীমাবদ্ধতা
- এই পরিবেশে Android SDK/Gradle build চালিয়ে APK তৈরি বা বাস্তব ফোনে পরীক্ষা করা হয়নি। তাই ZIP-টি source project; এটি APK নয়, এবং build সফল হবে বলে যাচাই করে নিশ্চয়তা দেওয়া যাচ্ছে না।
- Manual overlay-তে দেখানো লাইন ব্যবহারকারী নিজে নিয়ন্ত্রণ করেন; এটি গেমের প্রকৃত physics বা aim data পড়ে না।
- Automatic Detection পরীক্ষামূলক; আলো/বোর্ড/UI-কে গুটি ভেবে ভুল করতে পারে। নির্ভরযোগ্য coin tracking বা Auto Play/স্বয়ংক্রিয়ভাবে ম্যাচ জেতার ফিচার এতে নেই।
- Android-এ অন্য অ্যাপের ওপর overlay এবং screen capture চালু করতে আলাদা অনুমতি দিতে হয়।
- পাসওয়ার্ডটি অ্যাপের source code-এ আছে; এটি নিরাপদ সার্ভার-ভিত্তিক authentication নয়।
