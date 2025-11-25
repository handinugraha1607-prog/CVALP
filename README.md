import React from "react";

// Single-file React component for a company profile website.
// Uses Tailwind CSS for styling (assumes Tailwind is available in hosting project).
// Default export is a functional component you can drop into a React app.

export default function CompanyProfileWebsite({
  company = {
    name: "PT. Sinar Karya Konstruksi",
    tagline: "Membangun Masa Depan yang Kokoh",
    about:
      "PT. Sinar Karya Konstruksi adalah perusahaan konstruksi terkemuka yang berfokus pada pembangunan infrastruktur, gedung bertingkat, kawasan industri, serta fasilitas publik. Kami mengutamakan kualitas, keselamatan, dan ketepatan waktu.",
    yearFounded: 2010,
    address: "Jl. Merdeka Raya No. 88, Jakarta",
    phone: "(021) 888-1234",
    email: "info@sinarkonstruksi.co.id",
    website: "www.sinarkonstruksi.co.id",
  },
  services = [
    { title: "Konstruksi Gedung", items: ["Perkantoran", "Hunian Bertingkat", "Rumah Sakit", "Fasilitas Pendidikan"] },
    { title: "Infrastruktur", items: ["Jalan & Jembatan", "Drainase", "Irigasi", "Fasilitas Umum"] },
    { title: "Konstruksi Industri", items: ["Pabrik", "Gudang", "Workshop"] },
    { title: "Renovasi & Improvement", items: ["Interior & Eksterior", "Penguatan Struktur", "Modernisasi Bangunan"] },
  ],
  advantages = [
    "Kualitas Terjamin",
    "Ketepatan Waktu",
    "Keselamatan Kerja Prioritas",
    "Teknologi Modern (BIM & Monitoring)",
    "Layanan Terintegrasi: desain - konstruksi - serah terima",
  ],
  portfolio = [
    { title: "Gedung Perkantoran 12 Lantai", place: "Jakarta" },
    { title: "Jalan Lingkar Utara", place: "Jawa Barat" },
    { title: "Renovasi RSUD", place: "Banten" },
    { title: "Pabrik Tekstil", place: "Jawa Tengah" },
  ],
}) {
  return (
    <div className="min-h-screen bg-gray-50 text-gray-900 font-sans">
      {/* NAVBAR */}
      <header className="bg-white shadow-sm sticky top-0 z-30">
        <div className="max-w-7xl mx-auto px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <div className="flex items-center gap-4">
              <div className="w-10 h-10 rounded-lg bg-gradient-to-r from-sky-600 to-cyan-400 flex items-center justify-center text-white font-bold">SK</div>
              <div>
                <h1 className="text-lg font-semibold">{company.name}</h1>
                <p className="text-xs text-gray-500">{company.tagline}</p>
              </div>
            </div>

            <nav className="hidden md:flex gap-6 items-center text-sm">
              <a href="#about" className="hover:text-sky-600">Tentang</a>
              <a href="#services" className="hover:text-sky-600">Layanan</a>
              <a href="#advantages" className="hover:text-sky-600">Keunggulan</a>
              <a href="#portfolio" className="hover:text-sky-600">Portofolio</a>
              <a href="#contact" className="text-white bg-sky-600 px-4 py-2 rounded-md hover:opacity-95">Kontak</a>
            </nav>

            <div className="md:hidden">{/* hamburger for small screens (no JS) */}
              <details className="relative">
                <summary className="cursor-pointer px-3 py-2 rounded-md bg-gray-100">Menu</summary>
                <div className="absolute right-0 mt-2 w-48 bg-white rounded-md shadow-lg p-2">
                  <a className="block px-3 py-2 hover:bg-gray-50 rounded" href="#about">Tentang</a>
                  <a className="block px-3 py-2 hover:bg-gray-50 rounded" href="#services">Layanan</a>
                  <a className="block px-3 py-2 hover:bg-gray-50 rounded" href="#advantages">Keunggulan</a>
                  <a className="block px-3 py-2 hover:bg-gray-50 rounded" href="#portfolio">Portofolio</a>
                  <a className="block px-3 py-2 hover:bg-gray-50 rounded" href="#contact">Kontak</a>
                </div>
              </details>
            </div>
          </div>
        </div>
      </header>

      {/* HERO */}
      <section className="bg-white">
        <div className="max-w-7xl mx-auto px-6 lg:px-8 py-16 lg:py-24 flex flex-col lg:flex-row gap-10 items-center">
          <div className="lg:w-1/2">
            <h2 className="text-3xl lg:text-4xl font-extrabold leading-tight">{company.name}</h2>
            <p className="mt-4 text-lg text-gray-600">{company.tagline} — Solusi konstruksi handal yang mengutamakan kualitas, keamanan, dan keberlanjutan.</p>

            <div className="mt-6 flex gap-4">
              <a href="#contact" className="inline-block bg-sky-600 text-white px-5 py-3 rounded-md font-medium">Hubungi Kami</a>
              <a href="#portfolio" className="inline-block border border-gray-300 px-5 py-3 rounded-md">Lihat Portofolio</a>
            </div>

            <div className="mt-8 grid grid-cols-2 gap-4">
              <div className="bg-gray-50 p-4 rounded-md">Tahun Berdiri<br /><strong>{company.yearFounded}</strong></div>
              <div className="bg-gray-50 p-4 rounded-md">Proyek Unggulan<br /><strong>{portfolio.length}+</strong></div>
            </div>
          </div>

          <div className="lg:w-1/2">
            <div className="w-full h-64 lg:h-80 rounded-lg overflow-hidden shadow-lg">
              <img src="https://images.unsplash.com/photo-1529429614820-9f0c3b6f0a5d?q=80&w=1600&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="construction" className="w-full h-full object-cover" />
            </div>
          </div>
        </div>
      </section>

      {/* ABOUT */}
      <section id="about" className="max-w-7xl mx-auto px-6 lg:px-8 py-12">
        <div className="grid lg:grid-cols-2 gap-8 items-center">
          <div>
            <h3 className="text-2xl font-semibold">Tentang Kami</h3>
            <p className="mt-4 text-gray-600 leading-relaxed">{company.about}</p>

            <ul className="mt-6 grid grid-cols-1 sm:grid-cols-2 gap-2">
              <li className="bg-white p-3 rounded shadow-sm">Alamat: {company.address}</li>
              <li className="bg-white p-3 rounded shadow-sm">Telepon: {company.phone}</li>
              <li className="bg-white p-3 rounded shadow-sm">Email: {company.email}</li>
              <li className="bg-white p-3 rounded shadow-sm">Website: {company.website}</li>
            </ul>
          </div>

          <div>
            <div className="bg-gradient-to-tr from-sky-50 to-white p-6 rounded-lg shadow">
              <h4 className="font-semibold">Visi</h4>
              <p className="mt-2 text-gray-600">Menjadi perusahaan konstruksi terpercaya di Indonesia yang unggul dalam kualitas, inovasi, dan keberlanjutan.</p>

              <h4 className="font-semibold mt-4">Misi</h4>
              <ul className="mt-2 list-disc list-inside text-gray-600">
                <li>Memberikan layanan konstruksi yang aman, efisien, dan berkualitas tinggi.</li>
                <li>Mengadopsi teknologi terbaru untuk meningkatkan produktivitas dan akurasi.</li>
                <li>Membangun hubungan jangka panjang dengan klien melalui komunikasi transparan.</li>
                <li>Mengembangkan sumber daya manusia yang profesional dan berintegritas.</li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      {/* SERVICES */}
      <section id="services" className="bg-white border-t">
        <div className="max-w-7xl mx-auto px-6 lg:px-8 py-12">
          <h3 className="text-2xl font-semibold">Layanan Kami</h3>
          <p className="mt-2 text-gray-600">Solusi lengkap dari perencanaan hingga serah terima.</p>

          <div className="mt-6 grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            {services.map((s) => (
              <div key={s.title} className="p-5 bg-gray-50 rounded-lg shadow-sm">
                <h4 className="font-semibold">{s.title}</h4>
                <ul className="mt-3 text-gray-600 list-disc list-inside">
                  {s.items.map((it) => (
                    <li key={it}>{it}</li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* ADVANTAGES */}
      <section id="advantages" className="max-w-7xl mx-auto px-6 lg:px-8 py-12">
        <h3 className="text-2xl font-semibold">Keunggulan Kami</h3>
        <div className="mt-6 grid md:grid-cols-2 gap-6">
          {advantages.map((a, idx) => (
            <div key={a} className="flex gap-4 items-start bg-white p-4 rounded shadow-sm">
              <div className="w-10 h-10 rounded-full bg-sky-100 flex items-center justify-center font-semibold text-sky-600">{idx + 1}</div>
              <div>
                <h4 className="font-medium">{a}</h4>
                <p className="text-sm text-gray-500 mt-1">{a} — kami memastikan penerapan melalui SOP, K3, dan teknologi monitoring.</p>
              </div>
            </div>
          ))}
        </div>
      </section>

      {/* PORTFOLIO */}
      <section id="portfolio" className="bg-white border-t">
        <div className="max-w-7xl mx-auto px-6 lg:px-8 py-12">
          <h3 className="text-2xl font-semibold">Portofolio Proyek</h3>
          <p className="mt-2 text-gray-600">Beberapa proyek unggulan kami:</p>

          <div className="mt-6 grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
            {portfolio.map((p) => (
              <article key={p.title} className="bg-gray-50 rounded-lg overflow-hidden shadow-sm">
                <div className="h-40 bg-gray-200 flex items-center justify-center">
                  <img src={`https://images.unsplash.com/photo-1526304640581-d334cdbbf45e?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder`} alt={p.title} className="w-full h-full object-cover" />
                </div>
                <div className="p-4">
                  <h4 className="font-semibold">{p.title}</h4>
                  <p className="text-sm text-gray-500 mt-1">{p.place}</p>
                </div>
              </article>
            ))}
          </div>
        </div>
      </section>

      {/* CONTACT */}
      <section id="contact" className="max-w-7xl mx-auto px-6 lg:px-8 py-12">
        <div className="grid lg:grid-cols-2 gap-8 items-start">
          <div>
            <h3 className="text-2xl font-semibold">Hubungi Kami</h3>
            <p className="mt-2 text-gray-600">Siap berdiskusi tentang proyek Anda? Isi form atau hubungi langsung kontak kami di bawah.</p>

            <div className="mt-6 bg-white p-6 rounded shadow-sm">
              <p className="font-medium">{company.name}</p>
              <p className="text-sm text-gray-600 mt-1">{company.address}</p>

              <div className="mt-4">
                <p className="text-sm">Telp: <strong>{company.phone}</strong></p>
                <p className="text-sm mt-1">Email: <strong>{company.email}</strong></p>
                <p className="text-sm mt-1">Website: <strong>{company.website}</strong></p>
              </div>
            </div>

            <div className="mt-6">
              <h4 className="font-semibold">Lokasi (contoh)</h4>
              <div className="mt-3 rounded overflow-hidden shadow-sm">
                <iframe
                  title="map"
                  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d126915.123456789!2d106.68943!3d-6.20000!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMzPCsDAwJzAwLjAiUyAxMDbCsDQxJzAwLjAiRQ!5e0!3m2!1sen!2sid!4v0000000000000"
                  className="w-full h-48 border-0"
                />
              </div>
            </div>
          </div>

          <div>
            <div className="bg-white p-6 rounded shadow-sm">
              <form onSubmit={(e) => { e.preventDefault(); alert('Form submitted (demo)'); }}>
                <label className="block text-sm font-medium">Nama</label>
                <input className="mt-1 block w-full border rounded p-2" placeholder="Nama Anda" required />

                <label className="block text-sm font-medium mt-4">Email</label>
                <input type="email" className="mt-1 block w-full border rounded p-2" placeholder="email@domain.com" required />

                <label className="block text-sm font-medium mt-4">Pesan</label>
                <textarea className="mt-1 block w-full border rounded p-2" rows="6" placeholder="Jelaskan kebutuhan proyek" required />

                <div className="mt-4">
                  <button type="submit" className="bg-sky-600 text-white px-4 py-2 rounded">Kirim Pesan</button>
                </div>
              </form>
            </div>

            <div className="mt-6 text-sm text-gray-500">Kami akan merespons dalam 1-2 hari kerja. (Contact form demo — hubungkan ke backend sesuai kebutuhan.)</div>
          </div>
        </div>
      </section>

      {/* FOOTER */}
      <footer className="bg-gray-900 text-gray-200 mt-12">
        <div className="max-w-7xl mx-auto px-6 lg:px-8 py-8 flex flex-col lg:flex-row justify-between items-center gap-4">
          <div>
            <div className="font-semibold">{company.name}</div>
            <div className="text-sm text-gray-400">&copy; {new Date().getFullYear()} {company.name}. Semua hak dilindungi.</div>
          </div>

          <div className="text-sm text-gray-400">{company.address} • {company.phone} • {company.email}</div>
        </div>
      </footer>
    </div>
  );
}
