# Bab 5 - Seleksi Kondisi

Suatu aksi dapat dilakukan berdasarkan kondisi-kondisi tertentu yang telah didefinisikan sebelumnya. Di dalam Pascal, seleksi kondisi akan sangat erat dengan `if-else` dan `case`.

### Seleksi If-Else ###

Struktur dasar dari seleksi ini adalah

```
{ seleksi dengan 1 kasus }
if (kondisi) then begin
    { statement yang ingin dijalankan berdasarkan kondisi.. }
end;

{ seleksi dengan 2 kasus }
if (kondisi) then begin
    { statement yang dijalankan ketika kondisi bernilai true.. }
end else begin
    { statement yang dijalankan ketika kondisi bernilai false.. }
end;

{ seleksi dengan lebih dari 2 kasus }
if (kondisi) then begin
    { statement yang dijalankan ketika kondisi bernilai true.. }
end else if (kondisi1) then begin
    { statement yang dijalankan ketika kondisi1 bernilai true.. }
end else if (kondisi2) then begin
    { statement yang dijalankan ketika kondisi2 bernilai true.. }
.
.
.
end else begin
    { statement yang dijalankan ketika semua kondisi bernilai false.. }
end;
```

Perhatikan contoh kode berikut..

```pas
var
    n : integer;

begin
    n := 100;
    if (n mod 2 = 0) then begin
        writeln('Bilangan genap');
    end else begin
        writeln('Bilangan ganjil');
    end;
end.
```

Potongan kode diatas akan menghasilkan output...

```
Bilangan genap
```

...karena nilai `n` memenuhi kondisi `100 mod 2 = 0`.

### Seleksi Case ###

Berbeda dengan seleksi `if-else`, seleksi `case` digunakan untuk memilih suatu statement berdasarkan pada nilai-nilai konstan yang telah didefinisikan di dalam blok `case`. Seleksi ini tidak boleh mengandung ekspresi logika apapun.

Contoh kode

```pas
var
    c : char;

begin
    { statement lain... }
    case c of
        { boleh menggunakan ekspresi range.. }
        'a'..'z': writeln('Huruf kecil');
        'A'..'Z': writeln('Huruf besar');
        '0'..'9': writeln('Angka');
        '+': writeln('Karakter +');
        '*': writeln('Karakter *');
        else writeln('Karakter lain');
    end;
end.
```

Output kode diatas bergantung pada nilai dari variabel `c`.
