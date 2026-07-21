# 🏠 AI Real Estate Assistant (n8n Workflow)

مساعد مبيعات عقاري ذكي يعمل عبر تلغرام، مبني على منصة [n8n](https://n8n.io). 
يجاوب على استفسارات العملاء بالاعتماد على قاعدة معرفة (RAG)، يؤهّل العملاء تلقائياً 
عبر نظام Lead Scoring، ويحفظ بيانات العملاء المؤهلين في Google Sheets.

## ✨ المزايا
- محادثة تفاعلية عبر بوت تلغرام باللغة العربية.
- الإجابة على أسئلة العملاء من قاعدة معرفة (Pinecone + Google Gemini Embeddings).
- تقييم العملاء تلقائياً (Hot / Warm / Cold Lead) بناءً على نية الشراء والميزانية وطريقة الدفع.
- حفظ بيانات العملاء المؤهلين تلقائياً في Google Sheets.
- ذاكرة محادثة لكل عميل عبر Session ID الخاص بمحادثة تلغرام.

## 🧩 المكونات التقنية
| المكون | الاستخدام |
|---|---|
| Telegram Trigger / Send Message | استقبال وإرسال الرسائل |
| AI Agent (LangChain) | العقل المدبر للمحادثة |
| Google Gemini Chat Model | نموذج اللغة |
| Pinecone Vector Store | قاعدة المعرفة (RAG) |
| Google Gemini Embeddings | تحويل النصوص لمتجهات |
| Google Sheets | حفظ بيانات العملاء المؤهلين |
| Google Drive | تحميل ملف المصدر لتغذية قاعدة المعرفة |

## ⚙️ متطلبات التشغيل
قبل استيراد هذا الـ workflow لحسابك على n8n، يجب توفير:
1. **Telegram Bot Token** (عبر [BotFather](https://t.me/BotFather)).
2. **Google Gemini API Key** (لنموذج اللغة والـ Embeddings).
3. **Pinecone Account** + Index جاهز لتخزين المتجهات.
4. **Google Drive** + ملف يحتوي بيانات المشاريع العقارية (PDF/DOCX).
5. **Google Sheet** لحفظ بيانات العملاء، بأعمدة: الاسم، رقم الهاتف، السكن، إلخ.

## 🚀 خطوات الإعداد
1. استورد ملف `ai-real-estate-assistant.json` داخل n8n (Import from File).
2. اربط كل Credential الخاص بك (Telegram, Google, Pinecone) بدلاً من الحقول الفارغة.
3. حدّث معرّف ملف Google Drive ومعرّف Google Sheet داخل العقدتين المخصصتين (استبدل `YOUR_GOOGLE_DRIVE_FILE_ID` و`YOUR_GOOGLE_SHEET_ID`).
4. فعّل الـ workflow (Active) واختبره عبر إرسال رسالة للبوت.

## 📸 لقطات من الاستخدام
راجع مجلد `screenshots/` لعرض المحادثة الفعلية على تلغرام وهيكل الـ workflow داخل n8n.

## ⚠️ ملاحظات أمان
- تم حذف كل الـ API Keys ومعرّفات الحسابات الحقيقية من هذا الملف.
- لا تشارك ملف الـ workflow بعد ربطه بحساباتك الحقيقية.

## 📄 الترخيص
هذا المشروع متاح للاستخدام والتعديل الحر (MIT License أو حسب رغبتك).