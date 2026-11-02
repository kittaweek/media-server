# media-server — Context สำหรับ AI

> เจ้าของ: Kittawee "Post" Kongpan (kittaweek) · repo ส่วนตัว · ตอบภาษาไทย สั้น กระชับ

## ใช้ทำอะไร
Jellyfin media server ด้วย Docker Compose (รันบนเครื่องส่วนตัว) · repo **public**

## โครงสร้าง
- `docker-compose.yaml` (service `jellyfin`) · `.env.example` (UID/GID, path) · `README.md` ขั้นตอน mount drive
- ไม่มีโค้ดแอป ไม่มี test

## คำสั่ง
- `cp .env.example .env` แล้วแก้ค่า · `docker compose up -d` · `docker compose down`
- ตรวจไฟล์: `docker compose config -q`

## หมายเหตุ
- mount media drive แบบ read-only (`ro`)
- image pin `jellyfin/jellyfin:10.11.11` · Dependabot (docker-compose) เสนออัปเกรดทุกวันจันทร์ · อัปเกรด Jellyfin ควรสำรอง `PATH_CONFIG` ก่อน

## กฎ
- ห้าม push ตรงเข้า `main` → เปิด PR เสมอ · merge แบบ squash เท่านั้น · branch ที่ merge แล้วลบอัตโนมัติ
- AI ตรวจและสรุปได้ แต่ **ไม่ merge เอง** (Post เป็นคน merge) · ไม่ใช้ auto-merge
- CI ต้องเขียวก่อน merge
- ห้าม commit secret / `.env` / `*.bak` / ข้อมูลจริง · ใส่ค่าตัวอย่างใน `.env.example` เท่านั้น
- pin version ทุกอย่าง (image, package, action) · ห้าม `:latest`
- Branch: `<type>/<slug>` (feat, fix, docs, chore) · Commit: Conventional Commits
- `.claude/settings.local.json` อยู่ใน `.gitignore` · ห้าม commit
