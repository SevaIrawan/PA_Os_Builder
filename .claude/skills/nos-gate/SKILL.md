---
name: nos-gate
description: Router Anchor 04 NOS. Pakai saat Bambang memberi key Jira (OSD-xxx, NSE-xxx, SSCSD-xxx) atau bertanya "tahap/Gate mana", "siapa yang memutuskan", "halaman mana yang harus dibaca", "boleh lanjut atau tidak". Skill ini menjalankan kontrak AI Anchor 04 §七 dan hanya membaca, tidak menulis apa pun.
---

# nos-gate: kontrak AI Anchor 04 §七 (hanya baca)

Sumber: Anchor 04, pageId **1676804100** §「七、AI 机器执行合同」 dan §「二、唯一开发流」. Snapshot ada di `docs/anchor-04.md`, peta ada di `docs/04-anchor-navigation.md`.
**Skill ini tidak menulis ke sistem mana pun.** Keluarannya hanya laporan untuk Bambang.

## Langkah

0. **Baca Anchor 04 terbaru** lewat Atlassian_Rovo (`getConfluencePage` 1676804100). Bandingkan lastModified-nya dengan `docs/anchor-04.md` (Sep 05, 2026).
   - Kalau berbeda: beri tahu Bambang, lalu **pakai isi halaman terbaru**, bukan snapshot.
   - Kalau halaman tidak bisa dibuka: berhenti.
1. **Jira** (§七.1). Baca task, Parent, issue hulu/hilir (link), status, assignee, dan **semua comment** sampai yang terakhir.
   - Feature/Epic OSD → Atlassian_MCP.
   - SSCSD → Atlassian_Rovo, karena akun pribadi tidak bisa melihatnya. Kalau hasilnya 0 atau ditolak, tulis "tidak terlihat oleh akun X". **Jangan** menyimpulkan "tidak ada" (07.06.1 E16).
   - 「Jira 未登记的进度不视为事实」.
2. **Tentukan tahap dan Gate** (§七.2). Petakan status Jira ke delapan tahap dan node OS 开发流 berdasarkan **halaman OS 开发流 Spec (1729200354) terbaru** (status halaman itu masih 「草拟」, sebutkan ini). Tabel di `docs/04-anchor-navigation.md` §2 hanya jadi petunjuk awal.
3. **Buka halaman 04.x/07.x** yang ditunjuk Gate itu. Catat setiap halaman yang benar-benar dibuka (pageId + lastModified). Halaman yang tidak dibuka ditulis "belum dibaca".
4. **Isi tujuh hal** (§七.3): Owner / pemicu / prasyarat / hasil kerja / bukti penerimaan / langkah berikutnya / pihak yang menahan. Kalau ada yang kosong, tulis "tidak diketahui (belum ada di sumber X)". **Jangan memakai persentase.**
5. **Spec dan build sheet** (§七.4): versi terbaru, link dua arah, hierarki, hak tulis.
6. **Pemicu pendaftaran** (§七.5, §五): ada objek yang harus didaftarkan tapi belum ada barisnya? Kalau ada → **berhenti mengaktifkan dan berhenti memindahkan Gate**.
7. **Label status** (§七.6): hanya 已验证／已完成但未验收／进行中／待决策／被阻塞／未开始, dan setiap label disertai bukti.
8. **Cek kondisi berhenti** (Anchor 04 强制停止条件). Kalau salah satu terpenuhi, sebutkan 阻塞对象, 阻塞人, dan 恢复条件.

## Format keluaran
```
Objek        : <key> — <judul>          (sumber: <tool>, <akun>, <waktu>)
Tahap / Gate : <tahap> / <node>          (sumber: 1729200354 …, 1676804100 §二)
Pemutus      : <nama> (<OR|AND>)         (sumber: …)
Sudah dibaca : <daftar pageId + lastModified>
Belum dibaca : <daftar>
Tujuh hal    : …
Status       : <salah satu dari 6 label> — bukti: …
Berhenti?    : ya/tidak — 阻塞对象 / 阻塞人 / 恢复条件
Kontradiksi  : <id dari docs/open-issues.md bila relevan>
```
Kalau ada kontradiksi antar-source yang ikut memengaruhi, sebutkan item-nya dari `docs/open-issues.md` dan **jangan memilih salah satu sisi**.
