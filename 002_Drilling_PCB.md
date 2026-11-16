## Drilling PCB

Proses pertama dalam membuat PCB yaitu dengan melubangi PCB terlebih dahulu sesuai desain yang sudah dibuat, agar memudahkan saat membuat jalur dengan Mesin Laser Fiber nanti.

1. Buka aplikasi FLATCAM di Laptop, pastikan anda sudah menginstall file FLATCAM yang sesuai dengan file FLATCAM yang ada di Repo Github ini di laptop anda.
2. Klik menu File -> Open -> Open Gerber atau menggunakan shortcut, tekan Ctrl + G di Keyboard, kemudian pilih file gerber dari project anda yang sudah disimpan di laptop. Di tahap ini, anda hanya perlu
 memilih file Board Outline, dan Bottom layernya saja (fungsinya hanya sebagai pemandu visual untuk drilling)
3. Kemudian buka file excellon anda dengan cara klik menu File -> Open -> Open Excellon atau menggunakan shortcut Ctrl + E. Pilih semua file .DRL anda
4. Setelah itu, jika penempatan file gerber dan excellon anda belum Center, pindahkan terlebih dahulu dengan cara Blok atau pilih semua file gerber dan excellon anda, kemudian klik menu Edit -> Move to Origin
   atau Klik shortcut Shift + O / Icon Target
5. Kemudian, blok/pilih semua file excellon anda, klik menu Edit -> Join Objects -> pilih "Join Excellon(s) -> Excellon", akan terbuat pile baru dengan nama "Combo Excellon"
6. Disable file excellon selain file "Combo Excellon tersebut" dengan cara klik kanan pada file tersebut -> Disable Plot
7. Lanjut, klik kanan pada file "Combo Excellon" -> Edit. Anda akan masuk ke menu edit dari file excellon anda
8. Buat semua diameter lubang nya sama, misal 0.8mm atau 1mm sesuai kebutuhan.
9. Setelah itu, tambahkan 4 lubang baru di 4 titik ujung board outline sebagai penanda atau acuan saat membuat jalur nanti. Cara menambahkan nya yaitu Klik +Add -> klik icon "+" di bar menu atas,
   arahkan dan klik pada 4 titik ujung board outline. Jika sudah, tekan "Esc" pada keyboard
10. Samakan diameter 4 lubang baru yang sudah dibuat dengan diameter lubang yang lain, jika sudah sama tidak perlu diubah.
11. Jika sudah, klik "Exit Editor" -> Pilih "Yes" untuk menyimpan perubahan.
!2. Setelah keluar dari halaman editor, klik "Drilling Tool" dan ubah parameter nya sebagai berikut:
    Cut Z         : -2
    Travel Z      :  5
    Spindle Speed : 10000
    End Move Z    : 15
    End Move X,Y  : 0,0
    Preprocessor  : grbl_11
    (parameter lain yang tidak disebutkan di atas dibiarkan default)
13. Cek kembali, jika sudah sama, klik "Generate CNCJob object" -> Save CNC Code -> Beri nama file yang mendeskripsikan gcode tersebut, misal "Drill-0.8mm-PCB-ECU.nc" -> Klik OK
