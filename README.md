# AOS — Kantor Virtual Agent AI (Prototipe)

Dashboard pemantauan sistem **multi-agent AI (Agentic AI Operating System)** yang divisualisasikan sebagai kantor virtual. Setiap agent AI tampil sebagai karyawan di ruangannya, dan setiap animasinya mengikuti aktivitas agent tersebut.

**Demo:** _https://aos-kantor-virtual.vercel.app/_

> Status: prototipe dengan **data simulasi**. Belum terhubung ke agent sungguhan.

## Yang disimulasikan
- **Orkestrator** menerima perintah dari WhatsApp, membagi tugas ke agent spesialis (riset, validasi, copywriting, prompt gambar), lalu mengirim ringkasan hasil kembali ke WhatsApp.
- **Human-in-the-loop:** setiap aksi berdampak keluar (L2), misalnya mempublikasikan iklan, wajib disetujui dulu. Permintaan yang tidak dijawab akan kedaluwarsa dan aksinya **tidak** dijalankan.
- **Agent CS WhatsApp** dengan aturan ketat: FAQ, status pesanan (hanya baca), dan link resmi dijawab otomatis. Refund, komplain, negosiasi, dan pertanyaan di luar FAQ diteruskan ke admin.
- **Agent Factory:** orkestrator mengusulkan agent baru (status DRAFT di Ruang HR), yang baru aktif setelah disetujui.
- Feed aktivitas real-time, papan tugas (kanban), meteran biaya token, penanganan kegagalan + coba ulang, dan rem darurat.

## Arsitektur target (versi produksi)
Claude Agent SDK (orkestrator & subagent) → hooks memancarkan event ke database → FastAPI + SSE → dashboard (React + Phaser 3). Kanal: WhatsApp Cloud API via n8n.

## Teknologi prototipe
Satu file HTML: HTML, CSS, dan JavaScript murni, tanpa dependensi dan tanpa build.

## Pembuat
**M Jauhary** — peneliti & praktisi agentic AI, otomasi, dan smart instrumentation (Yogyakarta).
