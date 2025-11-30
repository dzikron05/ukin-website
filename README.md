# ukin-website
Website profil &amp; portofolio UKIN (Uji Kinerja) — Layanan Video Edukasi
ukin-website/
├─ index.html
├─ package.json
├─ postcss.config.cjs
├─ tailwind.config.cjs
├─ vite.config.js
└─ src/
   ├─ main.jsx
   ├─ App.jsx
   ├─ data/
   │  └─ portfolio.js
   └─ index.css
{
  "name": "ukin-website",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "autoprefixer": "^10.4.14",
    "postcss": "^8.4.24",
    "tailwindcss": "^3.4.8",
    "vite": "^5.0.0"
  }
}
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: { port: 5173 }
})
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
}
module.exports = {
  content: ['./index.html', './src/**/*.{js,jsx}'],
  theme: {
    extend: {
      colors: {
        ukinNavy: '#0b2545',   // biru dongker
        ukinGold: '#D4AF37'    // emas subtle
      }
    }
  },
  plugins: []
}
<!doctype html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1.0" />
    <title>UKIN — Produksi Video Edukatif Berkualitas</title>
  </head>
  <body class="bg-ukinNavy text-white">
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
@tailwind base;
@tailwind components;
@tailwind utilities;

/* small visual tweaks */
body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(180deg, #07182e 0%, #0b2545 100%);
}
import React from 'react'
import { createRoot } from 'react-dom/client'
import App from './App'
import './index.css'

createRoot(document.getElementById('root')).render(<App />)
export const portfolioItems = [
  {
    id: 1,
    title: 'Video Pembelajaran: Teks Deskripsi (Contoh)',
    description: 'Durasi: 5 menit — Animasi + Narasi untuk kelas 7',
    thumbnail: 'https://via.placeholder.com/800x450/07182e/ffffff?text=Thumbnail+1',
    link: '#' // nanti ganti ke YouTube / Drive
  },
  {
    id: 2,
    title: 'Microlearning: Cara Menulis Ringkasan',
    description: 'Durasi: 3 menit — Konsep & contoh',
    thumbnail: 'https://via.placeholder.com/800x450/07182e/ffffff?text=Thumbnail+2',
    link: '#'
  },
  {
    id: 3,
    title: 'Video Demo: Observasi Sederhana di Kelas',
    description: 'Durasi: 6 menit',
    thumbnail: 'https://via.placeholder.com/800x450/07182e/ffffff?text=Thumbnail+3',
    link: '#'
  }
]
import React from 'react'
import { portfolioItems } from './data/portfolio'

export default function App() {
  return (
    <div className="min-h-screen text-white">
      <header className="sticky top-0 z-50 bg-black/20 backdrop-blur-md border-b border-white/10">
        <div className="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
          <a href="#" className="flex items-center gap-3">
            <div className="w-10 h-10 rounded-lg bg-gradient-to-br from-ukinGold/80 to-ukinGold/60 flex items-center justify-center shadow">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none"><circle cx="12" cy="7" r="2.5" fill="#07182e"/></svg>
            </div>
            <div>
              <div className="font-semibold text-lg">UKIN</div>
              <div className="text-xs text-white/60">Uji Kinerja — Video Pendidikan Profesional</div>
            </div>
          </a>

          <nav className="hidden md:flex gap-6 items-center text-sm">
            <a href="#services" className="hover:text-ukinGold">Layanan</a>
            <a href="#works" className="hover:text-ukinGold">Portofolio</a>
            <a href="#about" className="hover:text-ukinGold">Tentang</a>
            <a href="#contact" className="px-4 py-2 bg-ukinGold text-ukinNavy rounded-md">Hubungi</a>
          </nav>
        </div>
      </header>

      <main>
        <section className="max-w-6xl mx-auto px-6 py-16 grid lg:grid-cols-2 gap-12 items-center">
          <div>
            <h1 className="text-3xl md:text-4xl font-extrabold leading-tight">UKIN — Produksi Video Edukatif Berkualitas</h1>
            <p className="mt-4 text-white/80">Kami mengubah materi pembelajaran Anda menjadi video yang jelas, menarik, dan mudah dipahami. Desain modern, narasi kuat, editing profesional.</p>
            <div className="mt-6 flex gap-4">
              <a href="#contact" className="px-5 py-3 bg-ukinGold text-ukinNavy rounded-md shadow">Pesan Sekarang</a>
              <a href="#works" className="px-5 py-3 border border-white/10 rounded-md">Lihat Portofolio</a>
            </div>
          </div>

          <div className="order-first lg:order-last">
            <div className="aspect-video rounded-xl overflow-hidden bg-gradient-to-br from-black/20 to-black/30 flex items-center justify-center">
              <div className="text-center p-6">
                <div className="mb-4 text-white/60">Contoh video pembelajaran</div>
                <div className="w-full max-w-md mx-auto bg-white/5 py-12 rounded-md">[Preview Video / Thumbnail]</div>
              </div>
            </div>
          </div>
        </section>

        <section id="services" className="bg-black/10 py-12">
          <div className="max-w-6xl mx-auto px-6">
            <h2 className="text-2xl font-bold">Layanan Kami</h2>
            <p className="mt-2 text-white/80">Solusi end-to-end untuk kebutuhan bahan ajar video.</p>

            <div className="mt-6 grid md:grid-cols-3 gap-6">
              <div className="p-6 bg-white/5 rounded-xl">
                <div className="font-semibold">Video Pembelajaran</div>
                <p className="mt-2 text-sm text-white/70">Naskah, rekaman, editing, subtitling.</p>
              </div>
              <div className="p-6 bg-white/5 rounded-xl">
                <div className="font-semibold">Slide & Modul Interaktif</div>
                <p className="mt-2 text-sm text-white/70">Word / PDF / PPT siap pakai.</p>
              </div>
              <div className="p-6 bg-white/5 rounded-xl">
                <div className="font-semibold">Konsultasi Kurikulum</div>
                <p className="mt-2 text-sm text-white/70">Penyesuaian materi sesuai standar.</p>
              </div>
            </div>
          </div>
        </section>

        <section id="works" className="max-w-6xl mx-auto px-6 py-12">
          <h3 className="text-2xl font-bold">Portofolio Singkat</h3>
          <p className="text-white/80 mt-2">Contoh proyek (dummy). Ganti thumbnail/tautan mudah lewat file <code>src/data/portfolio.js</code>.</p>

          <div className="mt-6 grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
            {portfolioItems.map((item) => (
              <a key={item.id} href={item.link} target="_blank" rel="noreferrer" className="bg-white/5 p-4 rounded-lg hover:scale-[1.01] transition">
                <img src={item.thumbnail} alt={item.title} className="h-40 w-full object-cover rounded-md" />
                <div className="mt-3">
                  <div className="font-semibold">{item.title}</div>
                  <div className="text-xs text-white/70 mt-1">{item.description}</div>
                </div>
              </a>
            ))}
          </div>
        </section>

        <section id="about" className="bg-black/10 py-12">
          <div className="max-w-4xl mx-auto px-6">
            <h3 className="text-2xl font-bold">Tentang UKIN</h3>
            <p className="mt-3 text-white/80">UKIN (Uji Kinerja) adalah layanan produksi video pendidikan yang membantu guru & mahasiswa menyampaikan materi lebih efektif. Dipimpin oleh Dzikron, dengan latar belakang pengajaran bahasa & videografi.</p>
          </div>
        </section>

        <section id="contact" className="max-w-6xl mx-auto px-6 py-12">
          <h3 className="text-2xl font-bold">Kontak & Pemesanan</h3>
          <p className="text-white/80 mt-2">Isi form atau hubungi via WhatsApp.</p>

          <div className="mt-6 grid md:grid-cols-2 gap-6">
            <form className="bg-white/5 p-6 rounded-lg">
              <label className="block text-sm">Nama</label>
              <input className="mt-2 w-full border border-white/10 rounded-md p-2 bg-transparent" placeholder="Nama Anda" />

              <label className="block text-sm mt-4">Email</label>
              <input className="mt-2 w-full border border-white/10 rounded-md p-2 bg-transparent" placeholder="email@contoh.com" />

              <label className="block text-sm mt-4">Pesan / Kebutuhan</label>
              <textarea className="mt-2 w-full border border-white/10 rounded-md p-2 bg-transparent" rows={4} placeholder="Deskripsikan kebutuhan video" />

              <div className="mt-4 flex gap-2">
                <button type="button" className="px-4 py-2 bg-ukinGold text-ukinNavy rounded-md">Kirim</button>
                <button type="reset" className="px-4 py-2 border border-white/10 rounded-md">Reset</button>
              </div>
            </form>

            <div className="bg-white/5 p-6 rounded-lg">
              <div className="font-semibold">Kontak</div>
              <div className="text-sm text-white/80 mt-2">Email: dzikron@example.com</div>
              <div className="text-sm text-white/80">WhatsApp: +62 812-3456-7890</div>
              <div className="mt-6">
                <div className="font-medium">Alamat</div>
                <div className="text-sm text-white/80">Yogyakarta, Indonesia</div>
              </div>
            </div>
          </div>
        </section>
      </main>

      <footer className="border-t border-white/10 mt-12">
        <div className="max-w-6xl mx-auto px-6 py-6 flex flex-col md:flex-row justify-between items-center text-sm text-white/70">
          <div>© {new Date().getFullYear()} UKIN — Dzikron. All rights reserved.</div>
          <div className="mt-3 md:mt-0">Built for educators • Simple • Minimal</div>
        </div>
      </footer>
    </div>
  )
}
# masuk ke folder
cd ukin-website

# jika kamu belum punya node_modules / package.json sebelumnya,
# tempel file package.json di atas, lalu:
npm install

# inisialisasi project Vite/Tailwind (kalau belum), tapi file2 sudah disediakan di atas
# Jalankan dev server untuk cek:
npm run dev
# buka http://localhost:5173 untuk lihat hasil

# jika OK, commit perubahan:
git add .
git commit -m "Add UKIN site (React + Tailwind dark theme)"
git push origin main
