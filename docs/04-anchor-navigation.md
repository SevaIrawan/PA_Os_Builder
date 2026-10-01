# Navigasi Anchor 04 & peta Gate

> **Sifat dokumen ini: peta penunjuk, bukan aturan.**
> Anchor 04 §六 berbunyi: 「任何页面不得复制另一个 SSOT 的值」. Karena itu file ini hanya berisi *di mana* aturan tinggal (pageId + bagian). *Isi* aturannya selalu dibaca dari halaman Confluence saat itu.
> 07 §二「锚点导向」: 「只有锚点页当下的导航表是权威入口」. Kalau file ini berbeda dengan Anchor 04 saat ini, **Anchor 04 yang benar**, dan file ini harus diperbarui.
>
> Snapshot dibuat 2026-09-26 dari source di `docs/sources.md`.

---

## 1. Cara masuk (urutan baca wajib)

Urutan ini diambil dari 07.06.1 §四 (pageId 1712226375) langkah 1, 07.06 §八 (1730347066), dan Anchor 04 §七 (1676804100):

1. **Jira dulu.** Baca task saat ini, Parent, issue hulu/hilir, status, Owner, comment, dan dependensi (Anchor 04 §七.1).
2. **07｜指南 §二 + §三** (1704362028): aturan umum dan format 标准缺口回报 (laporan celah standar). Tidak boleh dilewati walaupun sudah hafal (07.06 §八).
3. **Halaman panduan tahap yang sedang dikerjakan** (tabel §3 di bawah). Contoh untuk build: 07.06 dibaca penuh.
4. **Anchor 04 §二**: tentukan Gate yang berlaku, lalu **buka** halaman 04.x yang ditunjuk §六. Link yang tidak dibuka dianggap belum dibaca (Anchor 04 §七.2).
5. **07.06.1 §三 主题速查表**: buka entri yang cocok dengan pekerjaan ini sebelum mulai (07.06 §八).

## 2. Delapan tahap ↔ node OS 开发流 ↔ status Jira ↔ pemutus

Sumber:
- Anchor 04 §二 (1676804100)
- OS 开发流｜流程 Spec §三 节点表 (1729200354)

⚠️ **OS 开发流 Spec berstatus 「草拟」**: 「生命周期状态：草拟（v40；频道口径 2026-09-26）」 (1729200354 §二, dibaca ulang 2026-09-26 sore. v39→v40 hanya mengubah channel: 治理频道 #nos-governance C0C0S5CD1S9; node, pemutus, dan marker tidak berubah). Setiap kali dipakai, baca versi terbarunya.

| # | Tahap (Anchor 04 §二) | Node OS 开发流 | Jira (Epic/Feature) | Siapa yang memutuskan | Mode |
|---|---|---|---|---|---|
| 1 | 盘点与切分 | N1 → N2 → N3 | Epic | HOD departemen (N3) | — |
| 2 | 切分审计 | N4 (mesin, n8n) → N5 (manusia) | Epic | Kayden **atau** Alden | OR (lihat kontradiksi K-2) |
| 3 | 设计 | N6 (spawn Feature dari Epic; Spec v40: 「N6 spawn 流程卡（Epic）」) → N7 | Epic → Feature | HOD / Owner alur | — |
| 4 | 结构审计 | N8 (mesin) → N9 (manusia) | Feature | Tanda tangan bisnis Kayden **dan** teknis Alden | AND |
| 5 | 对齐 | N10 (brief mesin) → N11 | Feature | Anchor 04 §二: 「流程 Owner；跨部门时含相关 HOD／管理层」. N11: tanda tangan oleh HOD lintas departemen (lajur N11); pemutus dan freeze oleh Owner alur (「获授权的 N11 对齐裁决人（＝该流程 Owner，规则见 07.05）」, Spec 1729200354 v40) | — |
| 6 | 开发 | N12 | Feature | Anchor 04 §二: 「Alden／BO 建造 Owner」. Lajur N12 di 1729200354: 「BO 建设团队」 | — |
| 7 | 验收审计 | N13 (mesin) → N14 (manusia) | Feature | Kayden **atau** Alden | OR (lihat kontradiksi K-2) |
| 8 | 上线 | N15 → N16 (penutupan) | Feature → Epic | Anchor 04 §二: 「流程 Owner＋BO 建造 Owner」. Lajur N15 di 1729200354: 「部门 HOD」; 执行载体: 「部门 HOD 与 BO 协作完成宣贯、上线…」 | — |

Aturan yang sama untuk ketiga audit (Anchor 04 §二): 「机器通过不等于 Gate 通过」. Kalau mesin menolak, item otomatis dikembalikan ke tahap kerja sebelumnya. Kalau mesin meloloskan, item tetap di status audit dan menunggu keputusan manusia. Semua keputusan dicatat hanya di Jira Epic/Feature Comment, **bukan di Slack** (Anchor 04 **§三**: 「三个审计 Gate 不使用 Slack：机器报告与人工裁决只追加到对应 Jira Epic／Feature Comment」).

### Marker yang dapat dibaca mesin (hanya yang terlihat di source)

| Marker | Tempat terlihat | Sumber |
|---|---|---|
| `OSD-RETURN/v1` | Pengembalian di N4, N8, N13 (n8n) dan N5, N9, N11, N14 (AI pemutus). Aturan 「一轮一标记」. Pengembalian N15→N12 (masalah masa observasi) dan pengembalian otomatis WIP di N7 **tidak disebut** membawa marker. | 1729200354 §三 |
| `OSD-CUT-MACHINE/v1` | Laporan N4 | 1729200354 §三 N4 |
| `OSD-CUT-DECISION/v1` | Keputusan akhir N5 | 1729200354 §三 N5 |
| `OSD-CUT-SPAWN/v2` | Epic Comment N6 | 1729200354 §三 N6 |
| `【OSD-FREEZE｜v1｜FROZEN】` | Freeze N11. Contoh nyata: OSD-116 c50009/c50013 | 07.05 (1744306526); OSD-116 |

Daftar lengkap marker ada di **04.12 / 机读标记总清单 (pageId 2091876367)**. Halaman itu sudah dibaca penuh 2026-09-28 (`docs/sources.md`, baris 04.12; open-issues U-2): isinya hanya marker OS 开发流 (OSD-*), tidak mengatur `[[nos-…]]`. Versi sekarang v7 (2026-09-30) belum dibaca.

## 3. Skill per tahap: dari mana sumbernya

Di NOS, Skill adalah bagian 「正式 Skill 原文」 di halaman panduan 07.x. Salinan di tempat lain hanya 「受控部署副本」 (07 §四). Setiap kali dijalankan, Skill harus membaca halaman terbaru. Kalau isinya berbeda: 「停止执行并报告『部署漂移』」 (07.06 §八).

| Tahap / node | Skill | Halaman sumber | Status per 2026-09-26 (dibaca) | Ada di repo ini? |
|---|---|---|---|---|
| N3 | 流程盘点与切分 Skill | 07.01 (1705508891) §八 | Berlaku | Tidak (peran HOD) |
| N4/N5 | 切分审计 Skill | 07.02 (1744306506) §十 | Final | Tidak (peran pemutus) |
| N7 | 流程设计 Skill | 07.03 (1695744021) §七 | 「正式原文」 | Tidak (peran HOD) |
| N8/N9 | 结构审计: mesin / tanda tangan bisnis / tanda tangan teknis | 07.04 (1744896004) §十 | Final | Tidak (peran Kayden/Alden) |
| N10/N11 | 跨部门对齐 Skill | 07.05 (1744306526) §七 | Sisi manusia berlaku | Tidak (peran Owner) |
| **N12** | **流程建设 Skill** | **07.06 (1730347066) §八** | 「正式原文」 | **Ya: `.claude/skills/build`** |
| N13/N14 | 验收审计 | 07.07 (1744896024) | v5 (2026-09-29): 「状态：草稿，未生效」; §九 memuat Skill N13/N14 yang 「生效状态：草稿，未生效」 | Tidak |
| sebelum N15 | 使用者指南设计 Skill | 07.08 (1736736804) | Placeholder, belum berlaku | Tidak |

Alasan hanya Skill build yang dibuat: Bambang adalah builder BO untuk S-05 (OSD-116 c50071, Kent: "Build per the build skill (07.06)"). Skill tahap lain milik peran lain.

## 4. Tabel pendaftaran: kapan harus mencatat ke mana

Isi aturannya ada di Anchor 04 §五 (lihat `docs/anchor-04.md`). Tempat mendaftar per jenis objek diambil dari 07.06.1 §六-4. Pengecualian: baris "Istilah" dari Anchor 04 §五, dan "Data Table" dari 04.9 §四.

| Objek | Tempat daftar | pageId |
|---|---|---|
| Istilah | 04.0 | 1676640265 |
| Project | 04.1 | 1676738564 |
| Request Type / Route | 04.7 | 1691254793 |
| Entitas / arsip | 04.8 | 1690140756 |
| n8n workflow / Data Table | 04.9 (三位一体) | 1693089805 |
| Objek bersama Jira | 04.10 | 1738735636 |
| Slack Channel | 04.11 (berdasarkan Channel ID) | 1764524046 (dibaca penuh 2026-09-28, `docs/sources.md`; versi sekarang v8 2026-09-30 belum dibaca) |
| Objek yang tidak punya tempat daftar | Lapor dengan format 07 §三, jangan buat tempat daftar sendiri | 07.06.1 §六-4 |

## 5. Ke mana bertanya

Tabel lengkapnya ada di 07 §三 (1704362028) dan 07.06 §三「建设与平台类问题归口表」 (1730347066). Garis besarnya, dari sumber yang sama:
- Masalah **satu kartu** → comment di kartu itu.
- Masalah **aturan/platform** → Slack #nos-bo (C0BRSTNNY4A).
- **Isi Spec** → @Owner alur di Feature Comment.
- **Platform / izin / n8n / kredensial** → @Alden.
- **Mesin audit salah menilai** → @Kent.
- **Salah satu baris di tempat daftar** → Owner yang tertulis di catatan kaki halaman itu.
