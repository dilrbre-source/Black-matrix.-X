# Run instructions (development)

هذه التعليمات مبدئية لبناء وتشغيل المشروع محليًا بعد رفع الشيفرة داخل مجلد `src/`.

متطلبات عامة
- git
- Docker (اختياري، إن رغبت تشغيل الحاوية)
- أدوات اللغة المناسبة (Node, Python, Go) حسب الشيفرة التي سترفعها

تشغيل محلي (افتراض مشروع بسيط داخل src/)
1. استنسخ المستودع:

   git clone https://github.com/dilrbre-source/Black-matrix.-X.git
   cd Black-matrix.-X
   git fetch origin setup/project-structure
   git checkout setup/project-structure

2. ضع الشيفرة داخل `src/` — مثال:
   - `src/index.js` لمشروع Node.js
   - `src/app.py` لمشروع Python
   - `src/main.go` لمشروع Go

3. نفّذ بناء/تشغيل حسب اللغة:
   - Node.js
     ```bash
     cd src
     npm install
     npm start
     ```
   - Python
     ```bash
     cd src
     python -m venv .venv
     source .venv/bin/activate
     pip install -r requirements.txt
     python app.py
     ```
   - Go
     ```bash
     cd src
     go build -o app
     ./app
     ```

4. تشغيل داخل Docker (عام):
   - من جذر المستودع:
     docker build -t black-matrix-x:latest .
     docker run --rm -p 8080:8080 black-matrix-x:latest

CI (GitHub Actions)
- يوجد workflow مبدئي في `.github/workflows/ci.yml` يقوم باكتشاف لغة المشروع داخل `src/` ويشغّل فحوصات lint أو اختبارات إن توفرت.

أضف ملاحظاتك عن كيفية تشغيل التطبيق والمنافذ والمتغيرات البيئية في `docs/run.md` أو مباشرة في README.
