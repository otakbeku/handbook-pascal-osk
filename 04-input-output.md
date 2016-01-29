# Bab 4 - Input Output Standar

Yang dimaksud dengan I/O standar adalah suatu input yang dilakukan melalui keyboard dan mengoutputkannya ke layar (data tersimpan sementara di memori).

Dalam Pascal, untuk melakukan input nilai kedalam nilai menggunakan `read()` maupun `readln()`. Keduanya mempunyai fungsi yang sama. Sedangkan untuk melakukan output ke stdout menggunakan `write()` maupun `writeln()`. Perbedaan `write()` dengan `writeln()` adalah posisi kursor setelah pencetakan. `writeln()` akan menghasilkan karakter newline (baris baru) `\n`, sedangkan `write()` tidak.

Perhatikan contoh kode berikut

```pas
begin
    write('Selamat Datang ');
    writeln('Di Pemrograman Pascal :)');
end.
```

Potongan kode diatas akan menghasilkan output

```
Selamat Datang Di Pemrograman Pascal
```

Untuk melakukan input, juga cukup mudah. Perhatikan contoh kode berikut.

```pas
var
    a, b : integer;

begin
    readln(a, b); { input 2 nilai, dipisah dengan spasi }
    writeln('Hasil perkalian ', a, ' dan ', b, ' adalah ', a * b);
end.
```

Contoh Input dan Output

```
in
2 20

out
Hasil perkalian 2 dan 20 adalah 40
```

Atau bisa dituliskan seperti ini

```pas
var
    a, b : integer;

begin
    { input 2 nilai, tiap input tekan Enter }
    readln(a);
    readln(b);
    writeln('Hasil perkalian ', a, ' dan ', b, ' adalah ', a * b);
end.
```

Contoh Input dan Output

```
in
2
20

out
Hasil perkalian 2 dan 20 adalah 40
```

**Perlu diingat**, input harus sesuai dengan tipe datanya, jika tidak maka akan error.

Contoh kode yang akan menghasilkan error

```pas
var
    s : integer;

begin
    s := '111';
end.
```

Jika `s` di assignkan nilai selain Integer, maka akan muncul error..

```
Error: Incompatible types: got "Constant String" expected "SmallInt"
```

Jika melalui `stdin`, akan menghasilkan `Runtime Error`.
