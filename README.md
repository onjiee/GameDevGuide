# GitHub Pages — คู่มือสำหรับมือใหม่

สไลด์และตัวอย่างโครงสร้างไฟล์สำหรับทำเว็บด้วย GitHub Pages

## โครงสร้างโปรเจกต์นี้

```
my-website/
├── README.md               ← ไฟล์นี้ (แสดงบน GitHub)
└── docs/                   ← GitHub Pages serve จากที่นี่
    ├── index.html          ← Homepage
    ├── slides.html         ← สไลด์สอน GitHub Pages
    ├── Lab01/
    │   ├── index.html      ← หน้าแนะนำ Lab01
    │   └── (ไฟล์ Godot export)
    ├── Lab02/
    │   └── index.html
    └── Lab03/
        └── index.html
```

## วิธีตั้งค่า GitHub Pages

1. ไปที่ **Settings → Pages**
2. Branch: `main`
3. Folder: `/docs`
4. กด Save

## URL ที่ได้

```
https://username.github.io/my-website/
https://username.github.io/my-website/slides.html
https://username.github.io/my-website/Lab01/
https://username.github.io/my-website/Lab02/
```

## กฎสำคัญ

| กฎ | รายละเอียด |
|---|---|
| ทุก folder ต้องมี index.html | ไม่มี = 404 ทันที |
| ชื่อ folder = URL path | Lab01/ → .../Lab01/ |
| ตัวพิมพ์เล็ก/ใหญ่สำคัญ | lab01 ≠ Lab01 |
| tag HTML ต้องปิดครบ | `<li><a href="...">ชื่อ</a></li>` |
