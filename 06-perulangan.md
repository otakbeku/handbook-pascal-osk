# Bab 6 - Perulangan

Ketika kita menjalankan suatu statement yang sama dalam satu blok secara berulang, kita bisa menggunakan blok perulangan agar efisien. Perhatikan kode berikut...

```pas
begin
    writeln(1);
    writeln(2);
    writeln(3);
    writeln(4);
    writeln(5);
end.
```

...itu untuk mencetak angka 1-5, masalahnya, kalau mencetak 10000 angka? Akan sangat tidak efisien menggunakan cara diatas.

Bandingkan dengan yang ini.

```pas
var
    i : integer;
begin
    for i := 1 to 10000 do begin
        writeln(i);
    end;
end.
```

Lebih efisien, bukan? Marilah kita langsung bahas jenis-jenis perulangan di Pascal.

### Perulangan For ###

Perulangan jenis ini digunakan untuk mengulang statement dengan jumlah yang pasti. Mengulang sebanyak 10 kali, 100 kali, fixed.

Kode diatas menggunakan perulangan `for`.

Bentuk umum dari perulangan ini adalah...

```
for variabel_counter := nilai_awal to nilai_akhir do begin
    { statement yang ingin diulang.. }
end;
```

`variabel_counter` bebas nama variabel nya..

Kode ini akan mengulang dari 1 hingga 10000

```pas
var
    i : integer;
begin
    for i := 1 to 10000 do begin
        writeln(i);
    end;
end.
```

Jika perulangannya menurun, maka seperti ini

```
for variabel_counter := nilai_awal downto nilai_akhir do begin
    { statement yang ingin diulang.. }
end;
```

Keyword `to` diganti dengan `downto`.

### Perulangan while ###

Perulangan jenis ini mensyaratkan adanya kondisi yang mana jika kondisi bernilai `true`, maka perulangan akan terus berjalan.

Jika kode di perulangan `for` diubah ke bentuk perulangan `while`, maka seperti ini...

```pas
var
    i : integer;

begin
    i := 1;
    while (i <= 10000) do begin
        writeln(i);
        i := i + 1;
    end;
end.
```

Link bagian ini [https://github.com/99ridho/handbook-pascal-osk/blob/master/06-perulangan.md#perulangan-while](https://github.com/99ridho/handbook-pascal-osk/blob/master/06-perulangan.md#perulangan-while)

Jika kondisi dalam perulangan `while` selalu `true`, maka akan mengakibatkan infinite loop.

### Perulangan Repeat-until ###

Perulangan jenis ini merupakan kebalikan dari `while`. Statement akan diulang jika kondisi masih bernilai `false`.

Jika kode di perulangan `while` diubah ke bentuk perulangan `repeat-until`, maka seperti ini...

```pas
var
    i : integer;

begin
    i := 1; { inisialisasi i dengan 1 }
    repeat
        writeln(i);
        i := i + 1; { increment nilai i sebanyak 1 }
    until (i > 10000); { perulangan berhenti jika i sudah melebihi 10000 }
end.
```

### Increment dan Decrement ###

Selain menggunakan operator aritmatika, untuk mengincrement/decrement nilai kita juga bisa menggunakan fungsi `inc()` untuk mengincrement dan `dec()` untuk mendecrement nilai.

```pas
var
    i : integer;

begin
    i := 1;
    i := i + 1; { bisa ditulis sebagai inc(i, 1) }
    inc(i, 2); { sama dengan i := i + 2 }
    dec(i, 3); { sama dengan i := i - 3 }
end.
```
