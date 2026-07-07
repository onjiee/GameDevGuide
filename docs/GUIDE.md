# คู่มือเพิ่ม Lab ใหม่

## โครงสร้างไฟล์ที่ต้องรู้

```
docs/
├── index.html          ← Homepage (แก้เพื่อเพิ่มลิงก์ Lab ใหม่)
├── slides.html         ← สไลด์สอน (ไม่ต้องแก้)
├── Lab01/
│   ├── index.html      ← หน้าแนะนำ (แบบ Intro) หรือ Redirect
│   ├── lab01.html      ← Godot export
│   ├── lab01.js        ← Godot export
│   └── lab01.wasm      ← Godot export
└── Lab02/
    └── index.html      ← แบบ Redirect ไปหา lab02.html ทันที
```

---

## วิธีเพิ่ม Lab ใหม่ (เช่น Lab04)

### ขั้นที่ 1 — สร้าง folder และ copy template

```
docs/Lab04/
```

เลือก index.html แบบใดแบบหนึ่ง:

**แบบ A — Intro Page** (มีหน้าแนะนำก่อนเข้าเกม)
```html
<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lab 04 — My Website</title>
<!-- copy style จาก Lab01/index.html -->
</head>
<body>
<div class="card">
  <div class="lab-num">Lab 04</div>
  <h1>ชื่องาน</h1>
  <p>คำอธิบาย</p>
  <a class="btn-play" href="lab04.html">▶ เล่นเลย</a>
  <a class="btn-back" href="../">← กลับ Homepage</a>
</div>
</body>
</html>
```

**แบบ B — Redirect** (กดลิงก์แล้วไปเกมทันที)
```html
<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta http-equiv="refresh" content="0; url=lab04.html">
<title>Lab 04</title>
</head>
<body>
  <a href="lab04.html">คลิกถ้าไม่ redirect อัตโนมัติ</a>
</body>
</html>
```

### ขั้นที่ 2 — วางไฟล์ Godot export

```
docs/Lab04/lab04.html
docs/Lab04/lab04.js
docs/Lab04/lab04.wasm
docs/Lab04/lab04.pck   ← (ถ้ามี)
```

### ขั้นที่ 3 — เพิ่มลิงก์ใน Homepage

เปิด `docs/index.html` หาส่วน Labs แล้วเพิ่ม:

```html
<a class="lab-card" href="Lab04/">
  <div class="left">
    <h2>Lab 04</h2>
    <p>คำอธิบาย Lab 04</p>
  </div>
  <span class="arrow">→</span>
</a>
```

---

## Root Mode vs Docs Mode

| | Root Mode | Docs Mode |
|---|---|---|
| ที่เก็บไฟล์ | ที่ root `/` | ใน `/docs/` |
| ตั้งค่า Pages | Branch: main → **/** | Branch: main → **/docs** |
| URL ที่ได้ | เหมือนกันทั้งคู่ | เหมือนกันทั้งคู่ |
| เหมาะกับ | repo ทำเว็บอย่างเดียว | repo มีโค้ดอื่นด้วย |

---

## กฎจำขึ้นใจ

1. **ทุก folder ต้องมี `index.html`** — ไม่มี = 404
2. **ชื่อ folder = URL path** — `Lab01/` → `.../Lab01/`
3. **ตัวพิมพ์เล็ก/ใหญ่สำคัญ** — `lab01` ≠ `Lab01`
4. **`../`** = ขึ้นไป 1 folder — ใช้ใน href ของปุ่มกลับ
5. **อย่าแก้ไฟล์ Godot export** — แก้เฉพาะ `index.html` ที่เราสร้างเอง
