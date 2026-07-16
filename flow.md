graph LR
    %% Definisi Aktor
    Aktor_Warga["Warga / Publik"]
    Aktor_Pegawai["Pegawai / Kepala Desa"]
    Aktor_Admin["Administrator"]

    %% Kategori Use Case Warga
    subgraph UC_Warga ["Use Cases - Warga (Halaman Publik)"]
        UC_W1("Melihat Halaman Beranda<br/>(Home/index)")
        UC_W2("Mengajukan Surat Online<br/>(Suratonline/index, ajukan)")
        UC_W3("Melacak Status Pengajuan Surat<br/>(Tracking/index, cari, list_by_nik, tracked)")
        UC_W4("Mengirim Laporan Pengaduan<br/>(Pelaporan/index, kirim_laporan)")
        UC_W5("Memeriksa Respons/Tanggapan Laporan<br/>(Laporan/cek_respons)")
        UC_W6("Melihat Transparansi APB Desa<br/>(Apb_front/index, detail)")
        UC_W7("Membaca Pengumuman Kelurahan<br/>(Pengumuman/index)")
        UC_W8("Melakukan Verifikasi Keaslian Surat via QR Code<br/>(Verifikasi/cek)")
    end

    %% Kategori Use Case Pegawai
    subgraph UC_Pegawai ["Use Cases - Pegawai (Dashboard Internal)"]
        UC_P1("Mengakses Dashboard Sistem<br/>(Dashboard/index)")
        UC_P2("Melakukan TTD / Update Status Surat Warga<br/>(Surat/surat_masuk, updateStatus)")
        UC_P3("Mengelola Surat Masuk Dinas<br/>(Surat/surat_keluar_lama, tambah_surat_masuk, dll)")
        UC_P4("Mengelola Surat Keluar Dinas<br/>(Surat/surat_keluar, tambah_surat_keluar, dll)")
        UC_P5("Mengelola Surat Keterangan Dinas<br/>(Surat/surat_keterangan, tambah_surat_keterangan, dll)")
        UC_P6("Menyimpan Tanda Tangan Elektronik Surat<br/>(Surat/simpan_ttd)")
        UC_P7("Melihat Laporan Pengaduan Warga<br/>(Laporan/index)")
    end

    %% Kategori Use Case Administrator
    subgraph UC_Admin ["Use Cases - Administrator (Manajemen Data Master)"]
        UC_A1("Mengelola Data Penduduk (CRUD)<br/>(Penduduk/*)")
        UC_A2("Mengelola Data Pegawai (CRUD)<br/>(Pegawai/*)")
        UC_A3("Mengelola Data Pengguna Aplikasi (CRUD)<br/>(User/*)")
        UC_A4("Mengelola Anggaran APB Desa (CRUD)<br/>(Apb/*)")
        UC_A5("Mengelola Profil & Struktur Kelurahan<br/>(Galery/*)")
        UC_A6("Mengelola Pengumuman Kelurahan (CRUD)<br/>(Pengumuman_surat/*)")
        UC_A7("Mengelola Dokumentasi Kegiatan (CRUD)<br/>(Dokumentasi/*)")
        UC_A8("Memberikan Feedback Laporan Pengaduan<br/>(Laporan/kirim_feedback)")
    end

    %% Asosiasi Hubungan Aktor ke Use Case
    Aktor_Warga --- UC_W1
    Aktor_Warga --- UC_W2
    Aktor_Warga --- UC_W3
    Aktor_Warga --- UC_W4
    Aktor_Warga --- UC_W5
    Aktor_Warga --- UC_W6
    Aktor_Warga --- UC_W7
    Aktor_Warga --- UC_W8

    Aktor_Pegawai --- UC_P1
    Aktor_Pegawai --- UC_P2
    Aktor_Pegawai --- UC_P3
    Aktor_Pegawai --- UC_P4
    Aktor_Pegawai --- UC_P5
    Aktor_Pegawai --- UC_P6
    Aktor_Pegawai --- UC_P7

    Aktor_Admin --- UC_P1
    Aktor_Admin --- UC_P2
    Aktor_Admin --- UC_P3
    Aktor_Admin --- UC_P4
    Aktor_Admin --- UC_P5
    Aktor_Admin --- UC_P6
    Aktor_Admin --- UC_P7
    Aktor_Admin --- UC_A1
    Aktor_Admin --- UC_A2
    Aktor_Admin --- UC_A3
    Aktor_Admin --- UC_A4
    Aktor_Admin --- UC_A5
    Aktor_Admin --- UC_A6
    Aktor_Admin --- UC_A7
    Aktor_Admin --- UC_A8
