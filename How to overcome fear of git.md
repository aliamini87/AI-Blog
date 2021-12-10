---
authors:
  - name: 
    email: 
    link:
    avatar: 
category:
date: 2021-12-10
description:
icon:
image: ..\static\shutterstock_250696570-Converted-1000x462.jpg
label: null
layout: default
order: 20
tags:
title:
visibility: public

---
# چگونه بر ترس خود از گیت غلبه کنیم

![](../static/pngwing.com2.png)

<div dir="rtl">

من هم مثل نگارنده این [مقاله](https://thedatafrog.com/en/articles/git-basics-local/) از جمله آدم هایی بودم که در مواجهه با گیت و پوش و پول و کامیت، همواره دچار استرس میشدم. البته به لطف این مقاله متوجه شدم که این ترس به جهلم به چگونگی کارکرد گیت مرتبط هست. پس از خواندن این مقاله به نظرم این ترس خیلی کم شد.
	
**نکته جالب:** وقتی دستورات گیت را اجرا میکنی یک سری کمک هایی مینویسه که بسیار کاربردی هستند. به آن ها دقت کن.

## دستورات مهم گیت
### git init
این دستور برای معمولا قبل از آغاز پروژه و قبل از این که کدی نوشته شود در فولدر مورد نظر اجرا میشود. این کد فولدر مرسوم گیت را میسازد و از این لحظه این پوشه تحت نظارت گیت است.
### git status
این دستور وضعیت فعلی فرایند توسعه را نشان میدهد و راهنمایی هایی نیز ارائه میدهد. این که چه فایل هایی تغییر کرده اند و این که کدام ها آماده برای کامیت هستند و کدام ها تحت پیگیری گیت نیستند.
### git diff
 تفاوت بین دایرکتوری فعلی و آخرین کامیت را نشان میدهد.
### git add
این دستور فایل هایی که در جلوی آن معرفی میشوند را به حالت استیج منتقل میکند. به این مفهوم که تغییرات آن ها در کامیت بعدی ثبت خواهد شد. دقت کنید که قبل از هر کامیت باید دوباره فایل های مورد نظر را به حالت استیج در آورد و کاری نیست که فقط یک دفعه انجام بدهیم و تمام. وقتی از این دستور استفاده کردیم، اگر دوباره status بگیریم تغییر رفتار گیت و راهنمایی آن مشخص است. در صورتی که بخواهیم همه فایل های فولدر را به حالت استیج ببریم میتوان از `git add -A` استفاده کرد.
### git commit -m 'comment'
دستور معروف گیت که باعث میشود که فایل های استیج شده تغییراتشان ذخیره شود. دقت کنید که بهتر است که هر کامیت یک شرح در مورد خصوصیات این کامیت داشته باشد.
دستور `git commit -am` به صورت اتومات تمام فایل های تغییر یافته را استیج و بعد کامیت را انجام می دهد. البته دقت کنید که اگر فایلی اضافه کرده باشید، با این دستور خود به خود به حالت استیج نمی رود و باید ابتدا  add شود.
### git show
نشان دهنده اطلاعات آخرین کامیت
- آی دی کامیت
- برنچ
- نویسنده و تاریخ و ... 
### git log
 تاریخچه کامیت ها در یک برنچ. البته اگر با `--all` استفاده شود، کامیت های همه برنچ ها را نشان میدهد. دقت کنید که کامیت هایی که متعلق به هیچ برنچی نیست نمایش داده نمی شوند. برای این گونه کامیت ها میتوانی به دستور `git reflog` مراجعه کنی.
### git checkout
 این دستور شما را وارد یک یک کامیت دیگر میکند. 
 ```bash
 git checkout <commit code>
 ```
یا دستور زیر شما را وارد سر یک برنچ می کند. ( جلوتر در مورد برنچ توضیح داده شده است ) اگر برنچی که نوشته اید وجود نداشته باشد، آن برنچ در همان جا ساخته میشود.
```bash
git checkout -b <branch name>
```
برای این که به سه کامیت قبل در برنچ فعلی برگردیم، میتوان از دستور زیر استفاده کرد.
```bash
git chekout HEAD~3
```

دقت کنید که وارد شدن به کامیت های قبلی، کاری است که در گیت به وارد شدن به detached HEAD مشهور است. یعنی این که شما وارد کامیتی شده اید که خودش HEAD هیچ شاخه ای نیست. شما در این حالت هم میتوانید تغییرات ایجاد کنید و کامیت کنید. ولی در نظر بگیرید که اگر بدون ساخت شاخه جدید این کامیت ها را رها کنید، این کامیت ها در هیچ برنچی نخواهند بود و حتی در `git log -all` هم نمایش داده نمی شوند. شما میتوانید با دستور
```git
git switch -c <newbranch> [<start point>]
```	
	
این تغییرات را تبدیل به شاخه جدید کنید. آنچه داخل `[ ]` آمده است اختیاری است. اگر نباشد از همان جایی که هستید برنچ ساخته میشود. ولی اگر فرض کنید جای دیگری باشید با این دستور میتوانید از نقطه هر کامیتی یک برنچ جدید بسازید و به آن سوییچ کنید.

### git tag
 تگ هم یک نشانگر است با این تفاوت که بر خلاف برنچ حرکت نمیکند و با کامیت می ماند. 
```git
git tag v0.0.1 ab86e28
```
دستور بالا در کامیت `ab86e28` یک تگ اضافه می کند.
از این به بعد میتوان به جای کد کامیت با این تگ در دستورات کار کرد.



 
## پچ چیست؟
پچ (patch) تغییرات دو فایل نسبت به یکدیگر است. به راحتی میتوان پچ را در یک فایل کپی کرد.
```bash
diff -u file.txt user.txt > patch.txt
cat patch.txt
```

![](../static/git_p1.png)

یک پچ به شکل بالاست. یعنی نشان میدهد که چه چیزی به فایل دوم اضافه و کم کنیم به فایل اول میرسیم.
همچنین میتوان با جمع زدن این اختلاف با فایل اول، به فایل دوم رسید.
```bash
patch -u file.txt patch.txt 
cat file.txt
```

البته همین کار را بین دو کامیت نیز میتوان انجام داد.
```bash
git diff commit1 commit2 > patch
git checkout commit1
git apply patch
```
 

## شاخه در گیت چیست؟ 
 branch در واقع یک نشانگر است به شاخه کامیتی که در حال حاضر فعال است. منظور این است که برنچ فقط یک نمایشگر است و با از بین رفتن آن هیچ کامیتی از بین نمی رود.
 برای دیدن لیست شاخه های یک پروژه میتوان از دستور زیر استفاده کرد.
 ```bash
 git branch
 ```
 
با دستور `git checkout -b <branch name>` میتوان یک شاخه جدید ایجاد کرد و وارد آن شاخه شد.
البته از دو دستور زیر نیز میتوان برای این کار استفاده کرد
```bash
git branch <branch name>
git switch <branch name>
```
همچنین میتوان با دستور زیر میتوان از یک نقطه اولیه مشخص برنچ درست کرد.
```bash
git branch <branchname> <start point>
```
این دستور هم کار مشابهی انجام می دهد
```bash
git switch -c <new branch> [<start point>]
```

- به راحتی میتوان در کامیت فعلی با این دستور ساده برنچ ساخت و خود به خود وارد آن برنچ شد. حالا میتوانید به راحتی برنچ مستر را پاک کنید بدون این که هیچ اتفاق خاصی بیفتد. بعدش میتوانید دوباره همین برنچ را ایجاد کنید. دستوری هم هست که تمام برنچ های موجود و آن برنچی که فعال است را نشان میدهد.
- در گیت اگر بخواهی به کامیت های عقب تر یک برنچ تغییرات ایجاد کنی باید به آن کامیت بروی برنچ جدید بزنی و تغییرات را آنجا اعمال کنی. البته این هم شدنی است که اول تغیرات بدهی و کامیت بزنی و ... و وقتی مطمئن شدی بعدش برنچ جدید بزنی. توضیحات بیش تر را در بخش توضیحات دستور `checkout` داداه ام.
 - دقت کنید که اگر بخواهید برنچ خود را عوض کنید حتما ابتدا باید تکلیف تغییراتی که داده اید و کامیت نکرده اید معلوم کنید. یا استش کنید و یا کامیت کنید. برای توضیح بیش تر در مورد استش که یک روش برای سیو کردن موقتی کاری است که هنوز آماده کامیت نیست به این [لینک](https://www.atlassian.com/git/tutorials/saving-changes/git-stash) مراجعه کنید.
 - میتوان برنچ های اضافی را با دستور زیر پاک کرد.
```bash
git branch -d branch1 branch2
```
**بسیار دقت کنید که برنچ فقط یک نشانگر است و با پاک کردن برنچ تنها نشانگر پاک میشود و خود کامیت ها پاک نمی شوند. در نتیجه بدون نگرانی نشانگرهایی که به آن ها نیاز ندارید را پاک کنید**

## کانفیگ دستورات گیت
 فایل .gitconfig که در خانه یوزر شما وجود دارد و در آنجا میتوانید یک سری تنظیمات دائمی انجام دهید. در حالت عادی  در آن ایمیل و اسم شما هم قرار گرفته است. من اون رو با پیشنهاد این مقاله به این فایل تغییر دادم:
```bash
[core]
 excludesfile = /Users/cbernet/.gitignore_global
 editor = nano
[user]
 name = Colin Bernet
 email = colin.bernet@cern.ch
 github = cbernet
[color]
 ui = true
[color "status"]
 added = yellow
 changed = green
 untracked = cyan
[alias]
 co = checkout
 b = branch -vv
 l = log --graph --all --abbrev-commit --date=relative --format=format:'%C(bold blue)%h%C(reset) %C(green)%ar %C(blue)%an%C(bold blue)%d%C(reset)%n        %C(white)%s%n'
 lt = log --graph --abbrev-commit --date=relative --format=format:'%C(bold blue)%h%C(reset) %C(green)%ar %C(blue)%an%C(bold blue)%d%C(reset)%n        %C(white)%s%n'
 l1 = log --pretty=oneline --decorate
 s = status

```

- با تنظیماتی که کردیم دستور  `git l` این خروجی را نشان میدهد.
	
![](../static/git_p2.png)
	
دقت کنید که اگر از دستور `git log` استفاده می کردیم به این شکل درختی نشان نمیداد. چون این دستوری که تعریف شده `git log` ساده نیست. بلکه گیت لاگ با یک سری آپشن است.

## مرج کردن دو شاخه در گیت
در نظر اول مرج یکی از ترسناک ترین قسمت های کار با ورژنینگ هست.  وقتی قار است یک برنچ ( `branch1` ) را با برنچ اصلی (`master`) مرج کنیم، ابتدا به برنچ اصلی میرویم و از دستور زیر استفاده می کنیم.
```bash
git merge <branch1>
```
در این لحظه است که با کانفلیکت مواجه میشویم. دقت کنید که کانفلیکت یک چیز کاملا نرمال است و در صورتی که دو فایل نسب به هم تغییرات داشته باشند ( و نه این که یکی فقط چیزی از دیگری بیش تر داشته باشد ) باید به صورت دستی حل شود. گیت در این حالت به حالت merging میرود و منتظر می ماند تا شما کانفلیکت را بر طرف کنید.
	
![](../static/git_p3.png)

در این حالت با گرفتن git status نشان داده می شود که در چه فایل هایی کانفلیکت وجود دارد.
در این حالت اگر فایلی که کانفلیکت در آن وجود دارد را باز کنید با شکل زیر مواجه میشوید.
	
![](../static/git_p4.png)

در ادیتورهای خاص مثل vscode که اصلا یک سری آپشن برای تغییر راحت تر هم به شما میدهند.
	
![](../static/git_p5.png)

به آپشن هایی که در بالای فایل داده شده است دقت کنید.
در ادامه هر تغییری بخواهید میدهید و در نهایت وقتی همه کانفلیکت ها برطرف شد، فایل را ذخیره کنید. سپس با دستور `git add` فایلی که اصلاح کرده اید را به کامیت add می کنید. بعدش هم دستور کامیت را میدهید. بعد از دستور کامیت این دو برنچ با یکدیگر مرج شده اند.









## مراجع
- https://thedatafrog.com/en/articles/git-basics-local/
- https://git-scm.com/docs/git-merge
- https://stackoverflow.com/questions/9984223/what-happens-to-git-commits-created-in-a-detached-head-state/15774498
- https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History
- https://git-scm.com/docs/git-switch
- https://git-scm.com/docs/git-branch 
- https://www.atlassian.com/git/tutorials/saving-changes/git-stash


</div>