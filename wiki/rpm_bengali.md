# [লিনাক্স] C Shell (csh) rpm ব্যবহার: প্যাকেজ ম্যানেজমেন্টের জন্য একটি শক্তিশালী টুল

## Overview
`rpm` (Red Hat Package Manager) একটি শক্তিশালী প্যাকেজ ম্যানেজমেন্ট টুল যা লিনাক্স সিস্টেমে সফটওয়্যার প্যাকেজ ইনস্টল, আপডেট, মুছে ফেলা এবং পরিচালনা করতে ব্যবহৃত হয়। এটি মূলত Red Hat ভিত্তিক ডিস্ট্রিবিউশনগুলিতে ব্যবহৃত হয়।

## Usage
`rpm` কমান্ডের মৌলিক সিনট্যাক্স হল:

```bash
rpm [options] [arguments]
```

## Common Options
- `-i` : নতুন প্যাকেজ ইনস্টল করতে।
- `-e` : একটি প্যাকেজ মুছে ফেলতে।
- `-U` : একটি প্যাকেজ আপডেট করতে।
- `-q` : প্যাকেজের তথ্য জানতে।
- `--help` : সাহায্য তথ্য দেখাতে।

## Common Examples
নিচে কিছু সাধারণ উদাহরণ দেওয়া হল:

1. একটি নতুন প্যাকেজ ইনস্টল করা:
   ```bash
   rpm -i package-name.rpm
   ```

2. একটি প্যাকেজ মুছে ফেলা:
   ```bash
   rpm -e package-name
   ```

3. একটি প্যাকেজ আপডেট করা:
   ```bash
   rpm -U package-name.rpm
   ```

4. ইনস্টল করা প্যাকেজের তালিকা দেখা:
   ```bash
   rpm -qa
   ```

5. একটি প্যাকেজের বিস্তারিত তথ্য দেখা:
   ```bash
   rpm -qi package-name
   ```

## Tips
- প্যাকেজ ইনস্টল করার আগে সবসময় প্যাকেজের নির্ভরতা পরীক্ষা করুন।
- `--help` অপশন ব্যবহার করে কমান্ডের সাহায্য তথ্য দেখতে ভুলবেন না।
- প্যাকেজ মুছে ফেলতে গেলে নিশ্চিত হন যে এটি অন্য কোনও প্যাকেজের উপর নির্ভরশীল নয়।