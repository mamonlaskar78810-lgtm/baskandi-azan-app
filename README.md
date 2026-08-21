# বাঁশকান্দি মাদ্রাসা আযান

শিলচর/কাছাড় ও সালমিয়া/হাওয়ালির জন্য বাংলা আযান ও নামাজের সময়সূচি অ্যাপের Flutter source project।

## লোকেশন

### 🇮🇳 শিলচর / কাছাড়
- Latitude: 24.8333
- Longitude: 92.7789
- Time zone: Asia/Kolkata
- Calculation: Karachi
- Asr: Hanafi

### 🇰🇼 সালমিয়া / হাওয়ালি
- Latitude: 29.3333
- Longitude: 48.0833
- Time zone: Asia/Kuwait
- Calculation: Umm Al-Qura

## ফিচার
- ৫ ওয়াক্তের নামাজের সময়
- পরবর্তী ওয়াক্তের কাউন্টডাউন
- প্রতিটি ওয়াক্তের আলাদা ON/OFF
- প্রতিটি ওয়াক্তে -১০ থেকে +১০ মিনিট adjustment
- Android local notification
- Exact alarm mode
- Reboot rescheduling support through flutter_local_notifications receiver
- বাংলা UI
- দুই লোকেশনে দ্রুত পরিবর্তন
- Karachi/Hanafi calculation for Silchar
- Umm Al-Qura for Salmiya
- সেহরি/ইফতার reminder UI

## চালানোর নিয়ম

```bash
flutter pub get
flutter run
```

Release APK:

```bash
flutter build apk --release
```

APK পাওয়া যাবে:
`build/app/outputs/flutter-apk/release/app-release.apk`

## গুরুত্বপূর্ণ

1. অ্যাপের সময় astronomical calculation থেকে আসে; কোনো এক দিনের স্থির সময় সারা বছর ব্যবহার করা হয় না।
2. স্থানীয় মসজিদের মাইকের সময়ের সঙ্গে পার্থক্য থাকলে Settings থেকে ±10 মিনিট adjustment করুন।
3. Android 12+ এ Exact Alarm অনুমতি প্রয়োজন হতে পারে।
4. ফোনের Battery Optimization অ্যাপের alarm আটকে দিলে Settings থেকে এই অ্যাপকে unrestricted/allow background activity দিন।
5. প্রকৃত আযানের অডিও ব্যবহার করতে `assets/` বা Android notification sound resource-এ অনুমোদিত/নিজস্ব আযান অডিও যোগ করুন। এই source-এ কপিরাইটযুক্ত কোনো আযান রেকর্ডিং অন্তর্ভুক্ত করা হয়নি।
6. ফোন পুরোপুরি বন্ধ থাকলে কোনো Android app সাধারণ অবস্থায় আযান বাজাতে পারে না; ফোন চালু হয়ে boot হলে scheduled alarms পুনরায় সক্রিয় করার ব্যবস্থা রাখা হয়েছে।

## ১৬ আগস্ট ২০২৬-এর শিলচর বড় মসজিদের দেওয়া reference সময়

- ফজর 03:56 AM
- যোহর 11:47 AM
- আসর 04:24 PM
- মাগরিব 06:16 PM
- ইশা 07:36 PM

এগুলো test/reference হিসেবে বিবেচনা করতে হবে; স্থায়ী timetable হিসেবে নয়।


## ডিজাইন

মূল স্ক্রিনটি আপনার দেওয়া উদাহরণ ছবির মতো:
- গাঢ় বেগুনি/পার্পল গ্রেডিয়েন্ট
- বড় কাউন্টডাউন ঘড়ি
- উপরে মসজিদ আইকন, লোকেশন ও সেটিংস
- তারিখ
- ফজর/যোহর/আসর/মাগরিব/ইশা তালিকা
- পরবর্তী ওয়াক্ত সাদা হাইলাইট
- বাংলা অ্যাপের নাম: **বাঁশকান্দি মাদ্রাসা আযান**

## আযান অডিও

নোটিফিকেশন সিস্টেমে sound চালু আছে, কিন্তু কোনো কপিরাইটযুক্ত আযান রেকর্ডিং এই source-এর সঙ্গে দেওয়া হয়নি। আপনি নিজের/অনুমোদিত `azan.mp3` যোগ করে Android notification channel-এর sound resource হিসেবে সেট করতে পারবেন।

## ১০০% নির্ভুলতা সম্পর্কে

কোনো astronomical calculation-কে স্থানীয় মসজিদের ঘোষিত জামাত/আযানের সময়ের সঙ্গে স্বয়ংক্রিয়ভাবে ১০০% একই বলা ঠিক নয়। Calculation method, coordinates, উচ্চতা, স্থানীয় timetable এবং মসজিদের নিজস্ব adjustment-এর কারণে পার্থক্য হতে পারে। এজন্য ±১০ মিনিট manual adjustment রাখা হয়েছে।
