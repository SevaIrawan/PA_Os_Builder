---
name: nos-check
description: Cek kesiapan NOS di repo ini. Pakai saat Bambang minta "check NOS", "cek koneksi", "cek drift", atau di awal sesi kerja. Skill ini memeriksa connector dan akun (07.06 环境就绪), lalu membandingkan snapshot di repo (docs/anchor-04.md, salinan skill build) dengan halaman Confluence terbaru. Hanya membaca.
---

# nos-check: kesiapan lingkungan dan drift (hanya baca)

**Skill ini tidak menulis ke sistem mana pun.** Hasilnya dilaporkan ke Bambang dalam bentuk tabel. Setiap baris berisi hasil, bukti (tool + waktu), dan status (OK / GAGAL / TIDAK BISA DICEK).

## Bagian A: kesiapan lingkungan
Dasar: 07.06 (1730347066) bagian 「环境就绪（新开发者首次接入）」. **Baca dulu bagian itu versi terbaru**, karena beberapa langkah masih 🔲 dan bisa berubah.

| # | Cek | Cara | Lolos jika |
|---|---|---|---|
| A1 | Rovo bisa membaca NOSM | Atlassian_Rovo `getConfluencePage` 1676804100 | Halaman terbaca |
| A2 | Akun Rovo | Atlassian_Rovo `atlassianUserInfo` | email = boteam001@nexmaxorg.com (Backend Operations) |
| A3 | Akun MCP | Atlassian_MCP `atlassianUserInfo` | accountId = 712020:0ec04d28-9941-4568-b144-a1c4f2dcf138 (Bambang) |
| A4 | cloudId | `getAccessibleAtlassianResources` (keduanya) | abf9cc08-e266-45bd-93b8-836e4a8c7aaa (nexmax.atlassian.net) |
| A5 | n8n MCP terhubung | `search_workflows` (limit kecil) | Daftar workflow keluar |
| A6 | Uji 07.06: 「打开 04.7 查某个请求类型归属哪个 Project」 | Buka 04.7 (1691254793), ambil satu baris | Baris dan Project-nya terbaca |
| A7 | Slack terbaca | `slack_read_channel` C0BRSTNNY4A limit 1 | Pesan terbaca |

Catatan:
- A2 dan A3 **berbeda akun**, dan itu memang disengaja (CLAUDE.md §2). Kalau salah satunya berubah, **berhenti** dan tanyakan ke Bambang sebelum menulis apa pun.
- Space NW (1647870014, 1656783199) **tidak boleh** dicoba dibuka. Kalau tidak ada akses, berarti dilarang.

## Bagian B: drift snapshot di repo terhadap Confluence
| # | Snapshot di repo | Sumber | Cara membandingkan |
|---|---|---|---|
| B1 | `docs/anchor-04.md` | 1676804100 | Ambil markdown halaman terbaru, lalu bandingkan isinya teks demi teks dengan isi file (di bawah komentar header). Laporkan setiap perbedaan dan lastModified baru. |
| B2 | `.claude/skills/build/SKILL.md` bagian "Salinan butir Skill" | 1730347066, judul 「流程建设 skill｜适用者：BO 建设团队」 | Bandingkan setiap butir dengan mengabaikan URL link. Kalau berbeda → 「部署漂移」. |
| B3 | `docs/sources.md` (lastModified halaman utama) | 04.x, 07, 07.06, 07.06.1, OS 开发流 Spec, build sheet S-05 | Laporkan halaman yang lastModified-nya berubah. Artinya halaman itu harus dibaca ulang sebelum dipakai. Ini **tidak otomatis berarti konflik** (07.06: 「版本变化只触发复核，不自动判冲突」). |

Kalau ada drift: **jangan memperbarui file di repo tanpa persetujuan Bambang.** Laporkan dulu perbedaannya.

## Bagian C: isu terbuka
Baca `docs/open-issues.md`. Untuk setiap item K-x atau U-x yang mungkin sudah berubah (misalnya halamannya diperbarui), sebutkan apakah perlu dicek ulang. Jangan menandai item sebagai selesai tanpa bukti.
