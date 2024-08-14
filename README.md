
### Default Admin Credentials.
- Email: admin@admin.com
- password: password


### Default System 
Penggunaan pesan cepat dalam aplikasi ini sebaiknya menggunakan kunci *status* untuk pesan yang berhasil dan kunci error untuk pesan yang gagal. Ada dua jenis pengamanan yang tersedia: *web* sebagai pengaturan standar dan admin sebagai pengaturan khusus. Untuk bagian otentikasi pengguna *admin*, gunakan `auth:admin` bagi mereka yang sudah masuk, dan gunakan `guest:admin` bagi yang belum masuk.

Aplikasi ini juga memiliki fitur khusus bernama `EnsureCustomGuardIsVerified`, yang berguna untuk memverifikasi email dari pengguna yang memakai pengaturan khusus. Fitur ini didaftarkan sebagai `guard.verified` dan membutuhkan dua hal: nama pengguna yang pertama dan nama rute yang kedua, yang akan mengarahkan pengguna yang belum diverifikasi. Contohnya adalah `guard.verified:admin,admin.verification.notice` atau `guard.verified:customer,customers.verify-notice`.

Untuk pengguna pengaturan standar, hindari penggunaan direktif `@auth` atau `@guest`. Sebagai gantinya, gunakan `Auth::guard('web')->check()` dengan `@if`. Terakhir, jalur untuk *Admin* dan *Default* dipisahkan, dan semua jalur untuk admin diawali dengan prefiks `admin`.
