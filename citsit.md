# Digital Laboratory FTUI - Citsit Pemrograman C

## Variables

### Tipe Data dan Variabel
- `int`: Menyimpan bilangan bulat. Identifier `%d`, `%i`, `%u`.
- `float`: Menyimpan bilangan berkoma. Identifier `%f`.
- `char`: Menyimpan karakter tunggal. Identifier `%c`.
- `bool`: Menyimpan nilai benar (`true`) atau salah (`false`).
- `string` (array of `char`): Menyimpan teks atau banyak karakter. Identifier `%s`.

### Type Casting
Type casting digunakan untuk mengubah tipe data dari satu tipe ke tipe lainnya.

```c
float a = 5.5;
int b = (int) a; // b = 5
```

> Thought Exercise: apa yang yang terjadi jika men type casting char ke int `int c = (int) 'A';`?

<br/>
<br/>

## Arrays
```c
int angka[5] = {1, 2, 3, 4, 5}; // Array bilangan bulat
char nama[10] = "Alice"; // Array karakter (string)
```

![array](https://cdn.discordapp.com/attachments/1169082776012730378/1217007292105359420/image.png?ex=6602755d&is=65f0005d&hm=bdcb05dc9586e4937723357176e7075ba2b927923a3143ea0e56098cadf08c08&)

Array disimpan dalam memori secara berurutan.

`angka` saja valuenya adalah address dari `angka[0]`.
![array](https://cdn.discordapp.com/attachments/1169082776012730378/1217008125727477870/image.png?ex=66027624&is=65f00124&hm=624e232591d21a8f8c1344ea5b6a34b6c84a6daeac3e13c1f12bdae88f62050a&)

maka dari itu untuk mengakses nilai dari array kita menggunakan tanda `[]` yang berarti "offset". Contoh:
![array](https://cdn.discordapp.com/attachments/1169082776012730378/1217008662175023174/image.png?ex=660276a3&is=65f001a3&hm=bc7d0e5032a5a9fac95d376f44ba5f81348512bd596333d202e41209fd4c6090&)

`[0]` berarti akses nilai yang terletak pada offset 0 dari address `angka`.
sama saja seperti akses nilai pada address `(angka + 0).`

`[1]` berarti akses nilai yang terletak pada address `(angka + 1)`.

*Array dan Memori lebih lanjut [disini](#memori-management--pointer).*

<br/>

## Input/Output
`scanf()` digunakan untuk input, sedangkan `printf()` digunakan untuk output.

### Syntax
```c
scanf("format", &variabel);
printf("format", variabel);
```
scanf() memerlukan alamat dari variabel sebagai argumen (jadi menggunakan `&`), sedangkan printf() tidak.

### Contoh
```c
int umur;
printf("Masukkan umur Anda: ");
scanf("%d", &umur); // menggunakan identifier %d karena umur adalah integer
printf("Umur Anda adalah: %d tahun.\n", umur); // menggunakan identifier %d untuk output
```

### Pengecualian String
Untuk memasukkan string, kita tidak perlu menggunakan `&` karena string adalah array.

```c
char nama[20];
printf("Masukkan nama Anda: ");
scanf("%s", nama); // Tidak perlu menggunakan & karena nama adalah array
printf("Halo, %s!\n", nama); // Menggunakan identifier %s untuk output
```

> Thougt Exercise: Apa yang terjadi jika kita menggunakan `&` dan `%c` pada `scanf("%c", &nama);`? 

<br/>
<br/>

## Conditional

### `if`, `else if`, `else`
Menggunakan kondisional `if` untuk membuat keputusan dalam kode C.

```c
int skor = 85;
if (skor > 90) {
    printf("Nilai A\n");
} else if (skor > 70) {
    printf("Nilai B\n");
} else {
    printf("Nilai C\n");
}
```

<br/>
<br/>

## Loops

### `for`, `while`

```c
// for loop
for(int i = 0; i < 10; i++) {
    printf("%d\n", i);
}
```
for loop memiliki tiga bagian: inisialisasi, kondisi, dan iterasi.
- Inisialisasi, kondisi awal. Contoh `int i = 0;`
- Kondisi, saat apa for tetap berjalan. Contoh `i < 10;`
- Iterasi, setiap pengulangan apa yang berubah. Contoh `i++`

> Thougt Exercise: apa yang terjadi jika `for (;;)`

```c
// while loop
int i = 0;
while(i < 10) {
    printf("%d\n", i);
    i++;
}
```

---
---
> In progress 

## Function

## Memori management & Pointer

## Stucts

## Others

