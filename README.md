# Cyber Challenge Lab

คัดกรองข้อความหลอกลวงภาษาไทย ด้วย AI บน Microsoft Foundry

แล็บสำหรับ Online Workshop 2 · Thailand Cyber & Digital Innovation Challenge
เสาร์ 28 พฤศจิกายน 2569 · 09.00–12.00 น. · อบรมออนไลน์ผ่าน Google Meet

## ไฟล์ในนี้

| ไฟล์ | คืออะไร |
|---|---|
| `lab_scam_triage_foundry.ipynb` | **แล็บหลัก (ไทย)** ใช้ gpt-5.4-mini และ gpt-5.5 บน Microsoft Foundry ใช้กับ Azure free account ได้ |
| `lab_scam_triage_foundry_en.ipynb` | แล็บหลัก ฉบับภาษาอังกฤษ |
| `lab_scam_triage_claude_foundry.ipynb` / `_en.ipynb` | ฉบับ Claude — **ต้องใช้ subscription แบบ pay-as-you-go** (บัญชี Free Trial มีโควตา Claude เป็น 0) |

## ก่อนวันอบรม (pre-work) — ต้องมี Azure ของตัวเอง

โครงการนี้ไม่มีผู้สนับสนุนค่าใช้จ่าย Azure ผู้เรียนสร้างบัญชีและ resource เอง (ทีมละหนึ่งบัญชีก็พอ)

1. **สมัคร Azure free account** ที่ https://azure.microsoft.com/free
   ต้องมีบัญชี Microsoft หรือ GitHub, เบอร์โทรศัพท์ และบัตรเครดิตหรือเดบิตที่ไม่ใช่แบบเติมเงิน
   ตอนสมัครระบบอาจกันวงเงินราว 1 ดอลลาร์ชั่วคราวแล้วคืนให้ (ไม่ใช่การตัดเงิน)
2. **สร้าง project ใน Microsoft Foundry** ที่ https://ai.azure.com ระบบจะสร้าง Foundry resource ให้พร้อมกัน
   ตั้งไว้ใน resource group แยกของแล็บ จะได้ลบทิ้งทั้งกลุ่มได้ง่ายหลังอบรม
3. **Deploy โมเดลสองตัว** จากแค็ตตาล็อกของ Foundry แบบ Global Standard และตั้งชื่อ deployment ให้ตรงกับชื่อโมเดล
   - `gpt-5.4-mini` — ด่านคัดกรองทุกข้อความ
   - `gpt-5.5` — ด่านวิเคราะห์ละเอียด · ถ้า deploy ไม่ได้เพราะไม่มีโควตา ให้ deploy `gpt-5.4` แทน แล้วแก้ `DEEP_MODEL` ใน notebook
   - ถ้าโมเดลไหนขึ้นว่าไม่มีโควตาใน region นั้น ให้ลองสร้าง project ใน region อื่น
4. **คัดลอก key และ endpoint** จากหน้า *Keys and Endpoint* ของ resource
   ชื่อ resource คือส่วนหน้าของ endpoint เช่น `https://my-scam-lab.openai.azure.com/` ชื่อคือ `my-scam-lab`
5. **ตั้งงบและแจ้งเตือน** ที่ Cost Management → Budgets ก่อนเริ่มใช้งาน

## เริ่มใช้งานในวันอบรม

1. กดปุ่ม **Code** สีเขียวด้านบน แล้วเลือกแท็บ **Codespaces**
2. กด **Create codespace on main** แล้วรอ 2–3 นาที
3. ถ้า VS Code ถามว่า *Do you trust the authors of the files in this folder?* ให้กด **Trust Folder & Continue**
4. เปิดไฟล์ `lab_scam_triage_foundry.ipynb` มุมขวาบนควรขึ้น **Python 3.11** ให้อัตโนมัติ
   ถ้ายังขึ้น *Select Kernel* ให้กด **Select Kernel → Python Environments... → Python 3.11** (`/usr/local/bin/python`)
5. ใส่ key และชื่อ resource ของคุณในเซลล์แรก แล้วทำตามทีละเซลล์

คู่มือทำตามทีละขั้น: https://training.codediva.co/workshops/cyber-challenge (รหัสเข้าดูแจ้งในห้องอบรม)

## กันไม่ให้เสียเงิน (อ่านให้ครบ)

- **Free account ไม่ตัดเงินเอง** เมื่อครบ 30 วันหรือใช้เครดิตหมด subscription จะถูกปิดใช้งาน ถ้าคุณไม่กด Upgrade
- **อย่ากด Upgrade to pay-as-you-go** ถ้ายังไม่ตั้งใจจ่ายเงินจริง
- **หลังอบรม ถ้าจะไม่ทำต่อ ลบ resource group ของแล็บ** Azure portal → Resource groups → เลือกกลุ่ม → Delete resource group
- **ถ้าจะเลิกใช้ Azure** Cost Management + Billing → Subscriptions → เลือก subscription → Cancel subscription
- **ห้าม commit key ลง repository** และห้ามวาง key ในแชต key ที่หลุดคือเงินในบัตรของคุณ
- หยุด Codespace ที่ https://github.com/codespaces เมื่อเลิกใช้

ข้อความตัวอย่างทั้งหมดแต่งขึ้นเพื่อการสอน เบอร์โทร ลิงก์ และเลขบัญชีเป็นของปลอม

---

วิทยากร นายเอกพงษ์ ขัติยะ · กรรมการผู้จัดการ บริษัท โค้ดดีวา จำกัด
Microsoft Partner · Microsoft AI Cloud Partner Program

---

## English

A hands-on lab: build an AI assistant that screens **Thai** scam messages, with AI models on Microsoft Foundry.
Online Workshop 2 · Thailand Cyber & Digital Innovation Challenge · Saturday 28 November 2026 · online via Google Meet

### Files

| File | What it is |
|---|---|
| `lab_scam_triage_foundry_en.ipynb` | **Main lab, English** — gpt-5.4-mini and gpt-5.5 on Microsoft Foundry; works on an Azure free account |
| `lab_scam_triage_foundry.ipynb` | Main lab, Thai |
| `lab_scam_triage_claude_foundry*.ipynb` | Claude edition — **requires a pay-as-you-go subscription** (a Free Trial has a Claude quota of 0) |

### Before the day (pre-work): your own Azure

There is no sponsor for Azure costs; each learner (or one person per team) sets up their own.

1. **Create an Azure free account** at https://azure.microsoft.com/free — you need a Microsoft or GitHub account,
   a phone number and a non-prepaid credit or debit card. Sign-up may place a temporary hold of about USD 1, which is released.
2. **Create a project in Microsoft Foundry** at https://ai.azure.com (it creates the Foundry resource too),
   in a resource group of its own so you can delete it in one go afterwards.
3. **Deploy two models** from the Foundry catalogue as Global Standard, naming each deployment after the model:
   `gpt-5.4-mini` (triage) and `gpt-5.5` (deep analysis). If `gpt-5.5` has no quota, deploy `gpt-5.4` and change `DEEP_MODEL`.
   If a model shows no quota in your region, try a project in another region.
4. **Copy the key and endpoint** from the resource's *Keys and Endpoint* page. The resource name is the first part of the
   endpoint: for `https://my-scam-lab.openai.azure.com/` it is `my-scam-lab`.
5. **Set a budget and alert** under Cost Management → Budgets before you start.

### On the day

1. Click the green **Code** button, then the **Codespaces** tab, then **Create codespace on main** (2–3 minutes)
2. If VS Code asks *Do you trust the authors of the files in this folder?*, click **Trust Folder & Continue**
3. Open **`lab_scam_triage_foundry_en.ipynb`**. Top right should already show **Python 3.11**; if it says *Select Kernel*, pick
   **Select Kernel → Python Environments... → Python 3.11** (`/usr/local/bin/python`)
4. Put your key and resource name in the first code cell, then run the cells one by one

Step-by-step guide: https://training.codediva.co/en/workshops/cyber-challenge (password given in the session)

### Avoiding charges

- **A free account never charges you on its own**: after 30 days or when the credit runs out, the subscription is disabled unless you upgrade
- **Do not press Upgrade to pay-as-you-go** unless you mean to pay
- **After the workshop, delete the lab's resource group**: Azure portal → Resource groups → your group → Delete resource group
- **Leaving Azure?** Cost Management + Billing → Subscriptions → your subscription → Cancel subscription
- **Never commit your key** or paste it in chat; a leaked key spends money on your card
- Stop your Codespace at https://github.com/codespaces when you are done

The sample messages are made up for teaching; every number, link and account in them is fake.
