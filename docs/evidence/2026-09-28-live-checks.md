# Bukti cek live, 2026-09-26 malam s.d. 2026-09-28: N20

Berisi hasil panggilan tool di sesi Claude Code yang sama dengan `2026-09-26-live-checks.md`. Penomoran E melanjutkan file itu. Nomor E di sini adalah nomor bukti repo, **bukan** entri 07.06.1.

Semua penulisan (n8n N20, build sheet) dilakukan atas perintah eksplisit Bambang di sesi ini:
- 「Tambahkan upstreamEvent ke N20 dulu」
- 「ya, update sticky note-nya」
- 「ya, jalankan 1 dan 2」
- 「jalankan keduanya」

Settings errorWorkflow/callerPolicy dipasang sendiri oleh Bambang lewat UI.

| # | Tool (connector) | Panggilan | Hasil (dikutip dari respons) |
|---|---|---|---|
| E16 | n8n `update_workflow` | N20 `ToIGnEJmksSPhC85`: input trigger `upstreamEvent`, diteruskan di "Check Already Triggered", field keenam di "Call Resignation Upstream Trigger Entry", sticky note dan description | 6 operasi diterapkan, `validationWarnings: []`. Hasil baca ulang: versionId `a967dc8b-def4-4ac4-9981-f8bf4c6b1a51`, updatedAt 2026-09-26T14:03:06.946Z, `active: false`, 10 node |
| E17 | n8n `get_workflow_details` | N20 setelah Bambang menyimpan Settings di UI | updatedAt 2026-09-28T00:52:29.474Z. `settings.errorWorkflow: VUIgv9Ujj1KEoIne`, `settings.callerPolicy: workflowsFromSameOwner`, ditambah `timeSavedMode: fixed`. Sebelumnya (baca 2026-09-26) kedua key itu tidak ada. |
| E18 | n8n `update_workflow` + `get_workflow_details` | Sticky note N20: kata "errorWorkflow" dihapus dari 「Not built yet」 | versionId `91e468a7-23df-4bc2-b234-8b6b5547fb83`, updatedAt 2026-09-28T00:54:33.799Z |
| E19 | n8n `get_workflow_details` | Entry Geri `qa01CkZBQfx8eLsK` (hanya baca) | `active: false`, versionId `ee6cb5fa-38bd-4939-8e15-5f39b2d229d1`, updatedAt 2026-09-26T12:55:57.987Z. Input trigger "Upstream Called": upstreamSource, upstreamEvent, upstreamCaseKey, employeeAccountId, dismissalCategoryId, judgmentRef. Field wajib di "Validate Upstream Input": upstreamSource, upstreamCaseKey, employeeAccountId, dismissalCategoryId. Daftar kategori yang diizinkan: '15846'…'15850'. |
| E20 | n8n `validate_node_config` | 5 node N20: N20 Trigger, Read S-05 Case Comments, Call…, Write Triggered Marker…, Already Triggered? | `valid: true` untuk kelimanya (cek skema saja) |
| E21 | Atlassian_MCP `executeRead` `listJiraIssueComments` | NSE-1137, 15 comment terbaru | total 272. Comment terbaru c50590 (Geri, 2026-09-26 19:55 +07). Tidak ada comment baru sampai 2026-09-28. |
| E22 | n8n `update_workflow` (`setNodeSettings`) + `get_workflow_details` | "Read S-05 Case Comments" `alwaysOutputData: true` | versionId `8937d700-f71c-4a08-89df-305c9d935bad`, updatedAt 2026-09-28T01:06:58.193Z, `active: false` |
| E23 | n8n `test_workflow` / `get_execution` | Tes kering, data di-pin | **17373**: satu item kosong di Read Comments, lalu `alreadyTriggered:false` dan alur sampai ke Write Marker. Call dan Write Marker `executionTime: 0` (di-pin). **17374**: marker `[[nos-s05-term:TEST-N20-DRY-2:TEST-RESIGN-OLD]]`, `alreadyTriggered:true`, alur berhenti di "Already Triggered?". Node Call tidak dipin otomatis oleh tool (`prepare_test_pin_data`: "skipped"), jadi dipin secara eksplisit. Daftar eksekusi entry terbaca 0 sebelum dan sesudah tes. Menurut 07.06.1 E16, angka 0 ini tidak dipakai sebagai bukti tunggal. |
| E24 | Atlassian_MCP `updateConfluenceContent` (akun pribadi Bambang) | Build sheet 2096463922, v51 → v52 | Satu dryRun, lalu tulis sungguhan. v52 dibuat 2026-09-28T01:14:41.690Z. Setelah `&quot;`/`&#39;` dinormalkan, baca ulang v52 sama persis dengan hasil dryRun. Perbedaan v51 ke v52 hanya 4 perubahan yang direncanakan: §五 7 paragraf, §一 sel status N20, 附表 baris 「先认领后动作」, §八 blok 「N20 干跑」. |

Batas bukti:
- Credential Bot_SSC di node N20 tidak tampil lewat API.
- Kondisi Jira benar-benar mengembalikan 0 comment tidak diamati langsung, karena node Read di-pin.
- Isi yang dikirim ke entry tidak terlihat, karena node Call di-pin.
