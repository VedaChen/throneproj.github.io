+++
title = "تنظیمات پیشرفته حالت TUN در ویندوز"
description = "کاهش ریسک نشت DNS در حالت TUN ویندوز با استفاده از سیاست های سیستم و تنظیمات مرورگر."
weight = 1

[extra]
+++

در این مطلب توضیح داده می شود که چگونه هنگام استفاده از حالت TUN در ویندوز، احتمال نشت DNS را کاهش دهید.

نشت DNS می تواند مقصد واقعی اتصال ها و فعالیت شبکه شما را آشکار کند، باعث کاهش حریم خصوصی شود، تحلیل ترافیک توسط ارائه دهنده اینترنت را آسان تر کند و حتی اثربخشی قوانین پروکسی را کاهش دهد.

## 1. غیرفعال کردن Smart Multi-Homed Name Resolution در ویندوز

در محیطی که کارت شبکه مجازی وجود دارد، امکان نشت DNS وجود دارد. چون چند رابط شبکه فعال هستند، ویندوز ممکن است برای解析 DNS از رابطی که سریع تر پاسخ می دهد استفاده کند و در نتیجه کارت شبکه مجازی دور زده شود.

پیشنهاد می شود این سیاست را غیرفعال کنید:

![غیرفعال کردن Smart Multi-Homed Name Resolution - مرحله 1](/images/windows-tun-dns-leak/step1-disable-smart-multi-homed.png)

![غیرفعال کردن Smart Multi-Homed Name Resolution - مرحله 2](/images/windows-tun-dns-leak/step2-group-policy.png)

![غیرفعال کردن Smart Multi-Homed Name Resolution - مرحله 3](/images/windows-tun-dns-leak/step3-policy-disabled.png)

## 2. غیرفعال کردن QUIC در مرورگر

برای نمونه در Chrome، این آدرس را در نوار آدرس وارد کنید:

`chrome://flags/`

عبارت `QUIC` را جستجو کنید و مقدار آن را روی `Disabled` بگذارید.

![غیرفعال کردن QUIC در مرورگر](/images/windows-tun-dns-leak/step4-disable-quic.png)
