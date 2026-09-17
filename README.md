# BS Dealer Pro (Bismillah Distribution Center)

ডিলারশিপ ম্যানেজমেন্ট অ্যাপ — ক্রয়/বিক্রয়, স্টক, ক্যাশ, ব্যাংক, পার্টি/সাপ্লাইয়ার হিসাব, ব্যালেন্স শীট ও লাভ-ক্ষতি রিপোর্ট।

এটি একটি সম্পূর্ণ **অফলাইন PWA** — কোনো সার্ভার/ব্যাকএন্ড ছাড়াই ব্রাউজারের `localStorage`-এ সব ডেটা সংরক্ষণ হয়। তাই GitHub Pages-এর মতো সাধারণ static hosting-এই এটি পুরোপুরি চলবে।

## GitHub-এ Deploy করার ধাপ

### ১. নতুন রিপোজিটরি তৈরি করুন
GitHub.com-এ লগইন করে একটি নতুন repository তৈরি করুন (যেমন `bdc-dealer-pro`), Public সিলেক্ট করুন। README/gitignore যোগ করার দরকার নেই।

### ২. আপনার কম্পিউটারে টার্মিনাল খুলে এই ফোল্ডারে যান, তারপর চালান:
```bash
git init
git add .
git commit -m "BDC Dealer Pro - initial deploy"
git branch -M main
git remote add origin https://github.com/<আপনার-ইউজারনেম>/<রিপো-নাম>.git
git push -u origin main
```

### ৩. GitHub Pages চালু করুন
1. আপনার রিপোজিটরির **Settings → Pages**-এ যান
2. "Build and deployment" → Source: **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)** সিলেক্ট করে **Save** চাপুন
4. ১-২ মিনিট পর আপনার অ্যাপ চলে যাবে:
   `https://<আপনার-ইউজারনেম>.github.io/<রিপো-নাম>/`

### পরে আপডেট করতে চাইলে
```bash
git add .
git commit -m "update"
git push
```
প্রতিটি push-এর পর GitHub Pages কয়েক মিনিটের মধ্যে স্বয়ংক্রিয়ভাবে নতুন ভার্সন প্রকাশ করবে।

## নোট
- এই অ্যাপের সব ডেটা প্রতিটি ব্যবহারকারীর নিজ ব্রাউজারে (localStorage) থাকে — কেউ একই লিংক অন্য ব্রাউজার/ডিভাইস থেকে খুললে আলাদা/খালি ডেটা দেখবে। একাধিক ডিভাইস/ব্যবহারকারীর মধ্যে ডেটা শেয়ার করতে হলে আলাদাভাবে ব্যাকএন্ড/ডাটাবেস যোগ করা প্রয়োজন হবে।
- `manifest.json` ও `sw.js` PWA হিসেবে ইনস্টলযোগ্য ও অফলাইন-ক্যাশযোগ্য করে রাখে।
