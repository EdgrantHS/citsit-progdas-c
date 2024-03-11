# Digital Laboratory FTUI - Citsit Pemrograman C

## Variables & Arrays
Variabel dapat menyimpan nilai secara sementara.  

Berikut adalah bagian dari README.md yang telah diperbarui sesuai dengan instruksi Anda:

---

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

## Arrays
```c
int angka[5] = {1, 2, 3, 4, 5}; // Array bilangan bulat
char nama[10] = "Alice"; // Array karakter (string)
```

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

## Conditional

Kondisional digunakan untuk mengendalikan alur eksekusi program berdasarkan kondisi tertentu.

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

## Loops

### `for`, `while`
Menggunakan loop untuk mengulang tugas yang sama berkali-kali.

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

## Common Mistakes

### Kesalahan pada Variabel dan Array
- Mendeklarasikan variabel tanpa tipe data yang tepat. `int umur;` (benar) vs `umur;` (salah).
- Mengakses indeks array di luar batas yang ditentukan. `int angka[5];` hanya memiliki indeks 0-4.
- Lupa menginisialisasi variabel atau array sebelum menggunakannya. 
```c
int umur; // tidak diinisialisasi

while (umur < 17) { // umur tidak diinisialisasi, hasilnya tidak terduga
  printf("Masukkan umur Anda: ");
  scanf("%d", &umur); // di sini umur baru ada nilai
  printf("Umur Anda adalah: %d tahun.\n", umur);
}
```

### Kesalahan dalam Input/Output
- Menggunakan `printf()` ketika seharusnya menggunakan `scanf()`, atau sebaliknya.
- Lupa menggunakan `&` (alamat dari operator) di depan variabel saat menggunakan `scanf()`.
- Salah memasukkan identifier dalam `scanf()`. Misalnya, menggunakan `%d` untuk `float` atau `%f` untuk `int`. Ini dapat menyebabkan hasil yang tidak terduga dan kesalahan program. 
> Jika Output anda 0, kemungkinan besar anda salah dalam memasukkan identifier dalam `scanf()` atau `prinf()` biasanya harusnya `%f`/`%lf` pakainya `%d` atau sebaliknya. 

Berikut adalah tambahan untuk bagian Common Mistakes dalam README.md, khususnya terkait kesalahan yang sering terjadi saat menggunakan struktur kontrol `while` dan `if` dalam pemrograman C:

---

## Common Mistakes

### Kesalahan dalam Penggunaan Variabel dan Array
- Mendeklarasikan variabel tanpa menentukan tipe data yang tepat.
- Mengakses indeks array yang melebihi batas yang ditetapkan.
- Lupa menginisialisasi variabel atau array sebelum digunakan.

### Kesalahan dalam Input/Output
- Salah menggunakan `printf()` untuk input atau `scanf()` untuk output.
- Lupa menggunakan `&` di depan variabel saat menggunakan `scanf()`.
- Salah memasukkan identifier dalam `scanf()` (misalnya, menggunakan `%d` untuk `float` atau `%f` untuk `int`).

### Kesalahan dalam Penanganan String
- Lupa menyisipkan karakter null terminator `\0` di akhir string.
- Menggunakan `=` untuk menyalin string alih-alih menggunakan fungsi `strcpy()` dari library `<string.h>`.
- Mengakses karakter di luar batas string yang telah ditetapkan.

### Kesalahan dalam Penggunaan Conditional (`if`)
- Tidak menggunakan kurung kurawal `{}` ketika blok `if` berisi lebih dari satu pernyataan, yang bisa menyebabkan logika yang tidak diinginkan.

```c
if (kondisi)
    printf("Baris pertama.\n");
    printf("Baris kedua.\n"); // Baris ini akan dijalankan tanpa memperhatikan kondisi, karena tidak termasuk dalam blok 'if'
```

Solusi yang benar adalah:

```c
if (kondisi) {
    printf("Baris pertama.\n");
    printf("Baris kedua.\n");
}
```

- Menempatkan titik koma `;` langsung setelah ekspresi kondisional dalam `if`, yang akan menyebabkan `if` tidak menjalankan blok kode yang seharusnya.


### Kesalahan dalam Penggunaan Loops (`while`, `for`)
- Sama seperti pada `if`, tidak menggunakan kurung kurawal `{}` ketika loop mengandung lebih dari satu pernyataan.

```c
while (kondisi)
    printf("Baris pertama dalam loop.\n");
    printf("Baris kedua dalam loop.\n"); // Ini akan dijalankan tanpa memperhatikan kondisi loop
```

- Menempatkan titik koma `;` setelah ekspresi dalam `while` atau `for` loop, yang menyebabkan loop menjadi loop kosong.

```c
while (kondisi);
{
    // Blok ini tidak terpengaruh oleh loop
}

for (int i = 0; i < 10; i++);
{
    // Blok ini juga tidak terpengaruh oleh loop
}
```

Dalam kedua kasus tersebut, loop tidak akan menjalankan blok kode yang seharusnya karena titik koma `;` langsung setelah kondisi loop.

---
---
> In progress 

## Function

## Memori management & Pointer

## Stucts

## Common Mistakes

## Others

