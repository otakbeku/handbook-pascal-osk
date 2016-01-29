# Bab 7 - Array

Struktur data Array memungkinkan kita menyimpan nilai lebih dari satu didalam satu variabel. Karakteristik dari array memiliki jumlah data yang statis, dengan kata lain, penyimpanan datanya terbatas. Untuk mengakali keterbatasan dari array, orang-orang telah banyak membuat struktur data sendiri, contohnya linked list yang memungkinkan kita menyimpan data dengan tidak terbatas.

Baiklah, di dalam Pascal untuk mendeklarasikan array sebagai berikut

```pas
var
    a : array [1..10] of integer; { mendeklarasikan array sebanyak 10 elemen.. }

begin
    a[1] := 10;
    a[2] := 11;
    ...
end.
```

Indeks array dalam Pascal dimulai dari 1. Jika di bahasa lain, seperti C, C++ maupun Java, indeks array dimulai dari 0.

### Mendeklarasikan Array yang Memiliki Nilai Default ###

Untuk mendeklarasikan array yang telah memiliki nilai-nilai default, seperti ini

```pas
var
    a : array [1..5] of integer = (1, 2, 3, 4, 5);
```

### Pengaksesan Elemen Array ###

Untuk mengakses sebuah elemen dari array, kita bisa menspesifikasikan nilai indeksnya, seperti ini dalam contoh kode berikut

```pas
var
    a : array [1..10] of integer; { mendeklarasikan array sebanyak 10 elemen.. }
    i : integer;

begin
    a[1] := 10; { assign elemen array ke-1 dengan nilai 10 }
    a[2] := 11; { assign elemen array ke-1 dengan nilai 11 }

    { looping dari 1 hingga berapa banyak elemen dari array a }
    for i := 1 to length(a) do begin
        write(a[i], ' ');
    end;

    writeln();
end.
```

Potongan kode diatas akan menghasilkan output

```
10 11 0 0 0 0 0 0 0 0
```

### Array Multidimensi ###

Setelah kita mengenal array satu dimensi seperti diatas, di bahasan ini kita akan mengenal array multidimensi. Namun pembahasan disini hanya dibatasi hingga array 2 dimensi (matriks).

Untuk mendeklarasikan matriks, caranya cukup mudah

```pas
var
    matrik : array [1..3, 1..3] of integer; { mendeklarasikan matriks 3x3 }
```

### Pengaksesan Elemen Matriks ###

Hampir sama dengan mengakses array 1 dimensi

```pas
var
    a : array [1..3, 1..3] of integer; { mendeklarasikan matriks 3x3 }
    i : integer;

begin
    a[1, 1] := 10; { assign elemen b=1, k=1 dengan nilai 10 }
    a[2, 3] := 11; { assign elemen b=2, k=3 dengan nilai 11 }
end.
```
