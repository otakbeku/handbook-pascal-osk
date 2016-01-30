# Bab 8 - Prosedur dan Fungsi

Dalam pembuatan program, seringkali kita menggunakan beberapa kode secara berulang. Kita bisa memecah kode program yang besar menjadi sub-sub program yang lebih kecil, agar tidak terjadi redundansi kode.

### Prosedur ###

Prosedur adalah sub program yang mana hanya dijalankan ketika dibutuhkan saja. Prosedur tidak bisa mengembalikan nilai atau tidak memiliki return type.

Prosedur dalam Pascal bisa dituliskan sebagai berikut

```
procedure nama_prosedur( {{ list parameter }} );
const
    { daftar konstanta, jika ada }
var
    { daftar variabel lokal, jika ada }
begin
    { kode }
end;
```

Contoh prosedur sederhana

```pas
procedure cetak_nama(nama : string);
begin
    writeln('Hai ', nama, ', salam kenal..');
end;
```

Ketika prosedur `cetak_nama` dipanggil dengan `cetak_nama('Joni')`, maka akan menghasilkan output

```
Hai Joni, salam kenal..
```

### Fungsi ###

Hampir sama dengan prosedur, fungsi bisa mengembalikan nilai. Ambil contoh persamaan `f(x) = 3x + 2`, ketika kita ubah kedalam blok fungsi di Pascal, akan seperti ini

```pas
function f(x : integer) : integer;
begin
    f := 3 * x + 2; { mengembalikan 3x + 2 }
end;
```

Jadi, anatomi dari fungsi hampir sama dengan prosedur

```pas
function nama_fungsi( {{ list parameter }} ) : return_type;
const
    { daftar konstanta, jika ada }
var
    { daftar variabel lokal, jika ada }
begin
    { kode }
end;
```

Perbedaannya, fungsi harus menyertakan return type (tipe data kembalian).

Contoh fungsi yang mengembalikan nilai faktorial dari `N`.

```pas
function faktorial(N : integer) : longint;
var
    i : integer;
    hasil : longint;
begin
    hasil := 1;
    for i := 1 to N do begin
        hasil := hasil * i;
    end;
    faktorial := hasil; { mengembalikan nilai dari variabel hasil }
end;
```

### Passing by value dan passing by reference ###

Ketika kode diatas adalah menerapkan passing by value (nilainya yang dipassing ke fungsi, variabel asli tidak diubah), contoh kode berikut menerapkan passing by reference.

```pas
procedure tes(var x : integer);
begin
    x := x + 3;
end;

var
    a : integer;
begin
    a := 100;
    writeln('Sebelum pemanggilan prosedur : ', a);
    tes(a);
    writeln('Setelah pemanggilan prosedur : ', a);
end.
```

Akan menghasilkan output

```
Sebelum pemanggilan prosedur : 100
Setelah pemanggilan prosedur : 103
```

Yang dilewatken ke prosedur `tes` adalah reference yang menunjuk ke alamat memori dari variabel `a`, sehingga nilai dari `a` berubah sesuai instruksi di blok `tes`.

Perbedaanya, terletak di dalam kurung tempat dimana kita mendeklarasikan parameter. Pada passing by value tidak menyertakan keyword `var`, sedangkan passing by reference menyertakan keyword `var`.

### Rekursif ###

Rekursif adalah suatu kondisi dimana prosedur atau fungsi dapat memangiil dirinya sendiri sesuai kriteria yang ditentukan sebelumnya. Dalam rekursif wajib terdapat 2 bagian, bagian basis dan rekuren.

Bagian basis adalah bagian yang membatasi agar tidak terjadi rekursif terlalu dalam (rekursif non stop), sedangkan bagian rekuren adalah bagian yang memanggil dirinya sendiri.

Ketika fungsi `faktorial` diatas diubah kedalam bentuk rekursif, akan seperti ini

```pas
function faktorial(N : integer) : longint;
begin
    if (N = 1) then begin
        faktorial := 1; { basis rekursif }
    end else begin
        faktorial := N * faktorial(N - 1); { basis rekuren }
    end;
end;
```

Ketika fungsi diatas dipanggil dengan `faktorial(5)`, maka akan mengalami proses kira-kira seperti ini

```
faktorial(5)
        = 5 * faktorial(4)
                      = 4 * faktorial(3)
                                    = 3 * faktorial(2)
                                                  = 2 * faktorial(1)
                                                                = 1

faktorial(5) = 5 * 4 * 3 * 2 * 1 = 120  
```

Contoh rekursif yang lain (bilangan fibonacci)

```pas
function fibonacci(N : integer) : longint;
begin
    if ((N = 1) or (N = 2)) then begin
        fibonacci := 1;
    end else begin
        fibonacci := fibonacci(N - 1) + fibonacci(N - 2);
    end;
end;
```
