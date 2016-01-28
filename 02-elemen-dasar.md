# Bab 2 - Elemen Dasar dalam Pascal

### Variabel dan Konstanta ###

Dalam bahasa pemrograman manapun, pasti akan dijumpai penggunaan variabel. Variabel adalah sebuah tempat untuk menyimpan nilai. Bahasa Pascal menganut strong typed variable dimana variabel tersebut hanya bisa diisi dengan nilai yang sesuai dengan tipe data yang telah dideklarasikan. Bahasan tipe data akan dibahas setelah ini.

Deklarasi variabel dalam Pascal sebagai berikut

```pas
var
    nama_variabel1, nama_variabel2,... : tipe_data;
```

Sedangkan konstanta adalah sebuah variabel yang memiliki nilai yang tetap/tidak bisa diubah. Deklarasi konstanta sebagai berikut

```pas
const
    NAMA_KONSTANTA = nilai_konstan;
```

Konvensi penamaan konstanta biasanya menggunakan uppercase untuk membedakan mana variabel biasa mana variabel konstan.

### Tipe Data ###

Ketika kita ingin menggunakan variabel untuk menyimpan nilai dengan tipe tertentu, maka variabel harus dideklarasikan dengan tipe data yang sesuai.

##### Tipe Data Bilangan Bulat ####

Tipe Data | Ukuran (byte) | Range
----------|---------------|--------
ShortInt | 1 | -128 s/d 127
Integer | 2 | -32.768 s/d 32.767
LongInt | 4 | -2.147.483.648 s/d 2.147.483.647
Byte | 1 | 0 s/d 255
Word | 2 | 0 s/d 65.535

##### Tipe Data Bilangan Real/Floating-point ####

Tipe Data | Ukuran (byte)
----------|---------------
Real | 6
Single | 4
Double | 8
Extended | 10
Comp | 8

##### Tipe Data Karakter #####

Tipe data `char` digunakan untuk menyimpan satu karakter saja, contoh `'A'`, `'$'`, dan lain sebagainya.

##### Tipe Data String #####

Berbeda dengan `char`, `string` digunakan untuk menyimpan lebih dari satu karakter atau menyimpan kata, contohnya "Pascal dan Delphi".

Sebenarnya masih banyak lagi tipe data, seperti tipe data bentukan maupun abstract data type. Namun pembahasan ini dibatasi hanya sampai tipe data primitif :)
