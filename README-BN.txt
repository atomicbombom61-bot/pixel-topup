PIXEL TOPUP WEBSITE — START HERE

এই প্যাকেজে আছে:
- index.html       : কাস্টমার/ইউজার ওয়েবসাইট
- admin.html       : আলাদা অ্যাডমিন প্যানেল
- SETUP-original.md: মূল সেটআপ নির্দেশনা

চালু করার আগে:
1) Firebase Console-এ নিজের Firebase project তৈরি/নির্বাচন করুন।
2) Authentication-এ Email/Password এবং Google provider enable করুন।
3) Realtime Database তৈরি করুন।
4) index.html ও admin.html-এর window.PIXEL_FIREBASE_CONFIG-এ নিজের Firebase Web config বসান।
5) ওয়েবসাইট HTTPS hosting-এ publish করুন; index.html হবে মূল পেজ। admin.html একই ফোল্ডারে রাখুন।
6) Admin account Firebase Authentication-এ তৈরি করে এবং database-এ admin অনুমতি ঠিকভাবে সেট করে তারপর admin.html ব্যবহার করুন।

গুরুত্বপূর্ণ নিরাপত্তা সতর্কতা:
- মূল SETUP guide-এ দেওয়া {".read":true,".write":"auth != null"} rules production-এর জন্য নিরাপদ নয়। এতে যেকোনো signed-in user ডাটাবেসের সব তথ্য পড়তে পারে এবং লিখতে পারে। সরাসরি লাইভ সাইটে এই rules publish করবেন না।
- Admin email/password বা Firebase project-এর মালিকানা এখানে যাচাই করা হয়নি। ডিফল্ট admin credentials public source code-এ উল্লেখ আছে; লাইভ করার আগে সেগুলো বদলান এবং Firebase Authentication/Realtime Database rules শক্তভাবে configure করুন।
- bKash/Nagad/Rocket পেমেন্ট এখানে স্বয়ংক্রিয়ভাবে যাচাই হয় না, যদি না আপনি বৈধ merchant gateway/API যুক্ত করেন। শুধু transaction ID জমা দেওয়া মানেই payment verified নয়।
- Player UID lookup/auto-like API-ও আলাদা API URL ও অনুমোদিত provider ছাড়া কাজ করবে না।

ডেটা:
এই আপলোডে আলাদা database.json বা rules.json ফাইল ছিল না। HTML ফাইলগুলোর মধ্যে DEFAULT_SEED_DATA এবং seed import ফাংশন রয়েছে; admin workspace থেকে সেটি import করার সুবিধা আছে। Import করার আগে Firebase project ও rules নিরাপদভাবে প্রস্তুত করুন।
