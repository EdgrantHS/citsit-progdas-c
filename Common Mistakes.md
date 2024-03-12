# Digital Laboratory FTUI - Common Mistakes

## Kesalahan pada Variabel dan Array
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

## Kesalahan dalam Input/Output
- Menggunakan `printf()` ketika seharusnya menggunakan `scanf()`, atau sebaliknya.
- Lupa menggunakan `&` (alamat dari operator) di depan variabel saat menggunakan `scanf()`.
- Salah memasukkan identifier dalam `scanf()`. Misalnya, menggunakan `%d` untuk `float` atau `%f` untuk `int`. Ini dapat menyebabkan hasil yang tidak terduga dan kesalahan program. 
> Jika Output anda 0, kemungkinan besar anda salah dalam memasukkan identifier dalam `scanf()` atau `prinf()` biasanya harusnya `%f`/`%lf` pakainya `%d` atau sebaliknya. 

## Kesalahan dalam Penanganan String
- Lupa menyisipkan karakter null terminator `\0` di akhir string.
- Menggunakan `=` untuk menyalin string alih-alih menggunakan fungsi `strcpy()` dari library `<string.h>`.
- Mengakses karakter di luar batas string yang telah ditetapkan.

## Kesalahan dalam Penggunaan Conditional (`if`)
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


## Kesalahan dalam Penggunaan Loops (`while`, `for`)
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
