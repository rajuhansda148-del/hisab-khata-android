# হিসাব খাতা — Android APK প্রকল্প

এটি Hisab Khata Version 2 ওয়েব অ্যাপের জন্য একটি Android WebView wrapper প্রকল্প। GitHub Actions ব্যবহার করে APK তৈরি করা যাবে।

## আগে জরুরি কাজ
Hatchable-এ প্রজেক্টটি বর্তমানে private visibility-তে আছে। সাধারণ ব্যবহারকারীর ফোনে অ্যাপ কাজ করাতে হলে Hatchable Console → Settings-এ গিয়ে প্রজেক্টের Visibility Public করতে হবে। নইলে অ্যাপে সাইন-ইন ওয়াল দেখা যেতে পারে।

## APK তৈরি করার উপায়
1. ZIP ফাইলটি extract করুন।
2. GitHub-এ একটি নতুন repository তৈরি করুন (যেমন `hisab-khata-android`)।
3. এই ZIP-এর ভেতরের ফাইলগুলো repository-তে upload/commit করুন।
4. GitHub repository-র **Actions** tab খুলুন।
5. `Build Hisab Khata APK` workflow শেষ হলে run খুলুন।
6. নিচের **Artifacts** অংশ থেকে `Hisab-Khata-debug-apk` download করুন এবং ZIP extract করে `app-debug.apk` নিন।
7. Android ফোনে APK খুলে ইনস্টল করুন। প্রয়োজন হলে Settings-এ “Install unknown apps” অনুমতি দিন।

## সীমাবদ্ধতা
- এই প্রকল্পের APK নিজে ওয়েব অ্যাপের URL খুলে। ইন্টারনেট দরকার।
- এটি signed Play Store release নয়; debug APK।
- ওয়েব অ্যাপের হিসাব ব্রাউজার/WebView-এর local storage-এ থাকে; app data clear/uninstall করলে হারাতে পারে। নিয়মিত JSON backup রাখুন।
- APK-টি এখানে সরাসরি compile করা হয়নি; GitHub Actions-এ build workflow দেওয়া আছে।
