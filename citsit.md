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

<br/>
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

