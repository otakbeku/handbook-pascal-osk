# Bab 3 - Operator

Operator digunakan untuk mengoperasikan nilai-nilai maupun variabel. Banyak macam operator disini, diantaranya operator assignment, operator aritmatika, operator logika, operator bitwise.

### Operator Assignment ###

Operator `:=` digunakan untuk menginisialisasi/memasukkan nilai dari sebuah variabel.

```pas
var
    x : integer;

begin
    x := 100; { assign variabel x dengan nilai 100 }
end.
```

### Operator Aritmatika ###

Operator jenis ini digunakan untuk melakukan penghitungan dalam suatu variabel.

Operator | Tipe Operand | Tipe Hasil | Contoh
---------|--------------|------------|--------
+ | integer, real | integer, real | a + b
- | integer, real | integer, real | a - b
* | integer, real | integer, real | a * b
/ | integer, real | integer, real | a / b
div | integer | integer | a div b
mod | integer | integer | a mod b

Operator `div` digunakan untuk pembagian, dan hasil nya akan dibulatkan ke bawah. Contoh : `10 div 3 = 3`. Sedangkan operator `mod` digunakan untuk mencari sisa bagi dari 2 bilangan, contoh `10 mod 3 = 1`.

### Operator Logika ###

Operator jenis ini digunakan untuk melakukan operasi yang berkaitan dengan nilai logika (true/false).

Operator | Jenis | Contoh
---------|-------|--------
not | Negasi | not (a<=b)
and | Konjungsi | (a<=b) and (b>=c)
or | Disjungsi | (a<=b) or (b>=c)
xor | Exclusive Disjunction | (a<=b) xor (b>=c)

##### Tabel Kebenaran not #####

A | not A
--|-------
true | false
false | true

##### Tabel Kebenaran and #####

A | B | A and B
--|--|-----------
true | true | true
true | false | false
false | true | false
false | false | false

##### Tabel Kebenaran or #####

A | B | A or B
--|--|-----------
true | true | true
true | false | true
false | true | true
false | false | false

##### Tabel Kebenaran xor #####

A | B | A xor B
--|--|-----------
true | true | false
true | false | true
false | true | true
false | false | false

### Operator Bitwise ###

Operator jenis ini digunakan untuk mengoperasikan tiap bit nilai.

Operator | Jenis Operasi | Contoh
---------|---------------|---------
not | bitwise not | not 1
and | bitwise and | 1 and 2
or | bitwise or | 1 or 2
xor | bitwise xor | 1 xor 2
shr | shift right | 1 shr 2
shl | shift left | 1 shl 2

Contoh...

```
8 and 3
0 0 0 0 1 0 0 0         8 dalam biner
0 0 0 0 0 0 1 1         3 dalam biner
---------------- and
0 0 0 0 0 0 0 0         hasil = 0

8 or 3
0 0 0 0 1 0 0 0         8 dalam biner
0 0 0 0 0 0 1 1         3 dalam biner
---------------- or
0 0 0 0 1 0 1 1         hasil = 11

8 xor 3
0 0 0 0 1 0 0 0         8 dalam biner
0 0 0 0 0 0 1 1         3 dalam biner
---------------- xor
0 0 0 0 1 0 1 1         hasil = 11
```

Bingung? Baca kembali tabel kebenaran diatas.

Untuk `shl`, rumus untuk menyelesaikan `a shl b` adalah `a * (2 ^ b)`, sedangkan rumus untuk `shr` adalah `a / (2 ^ b)`.
