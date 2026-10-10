![Gambar 1](screenshot/Screenshot%202026-10-10%20183054.png)
1. Eksperimen Properti dan Nilai CSS
Eksperimen dengan CSS dapat dilakukan dengan memodifikasi atau menambahkan berbagai properti dasar berdasarkan panduan Cheat Sheet CSS.

Langkah Kerja: Anda dapat mengubah nilai properti yang ada (misalnya mengubah color: black; menjadi color: #2c3e50; atau mengubah font-size: 12px; menjadi 1rem;) serta menambahkan properti baru seperti border, box-shadow, atau border-radius.

Tujuan: Untuk melihat secara langsung bagaimana perubahan nilai dan penambahan properti memengaruhi tampilan visual elemen pada peramban (browser).

2. Perbedaan h1 {...} dan #intro h1 {...}
h1 {...} (Element/Type Selector):

Berfungsi untuk memilih seluruh elemen <h1> di dalam dokumen HTML, tanpa memedulikan di mana posisi atau di dalam kontainer apa elemen tersebut berada.

#intro h1 {...} (Descendant Selector):

Hanya memilih elemen <h1> yang berada di dalam elemen lain yang memiliki atribut ID intro (id="intro").

Memiliki tingkat spesifisitas (specificity) yang lebih tinggi dibandingkan element selector biasa. Jika ada properti yang sama, aturan pada #intro h1 akan menimpa aturan pada h1.

3. Prioritas CSS: Inline, Internal, dan Eksternal
Jika terdapat deklarasi Internal CSS, External CSS, dan Inline CSS pada elemen yang sama, Inline CSS yang akan ditampilkan oleh browser.

Penjelasan & Urutan Prioritas (Dari yang Paling Tinggi):
Inline CSS: Ditulis langsung pada atribut style="" di dalam elemen HTML. Memiliki prioritas paling tinggi.

Internal CSS & External CSS: Ditentukan berdasarkan urutan pemuatan (cascade order). Jika Internal CSS ditulis setelah tautan External CSS di dalam bagian <head>, maka Internal CSS akan menimpa External CSS (dan sebaliknya). Namun, keduanya tetap akan kalah jika elemen tersebut memiliki Inline CSS.

Contoh Kode:
HTML
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Prioritas CSS</title>
    <!-- External CSS (contoh di file eksternal: p { color: blue; }) -->
    <link rel="stylesheet" href="style.css">
    
    <!-- Internal CSS -->
    <style>
        p { color: green; }
    </style>
</head>
<body>
    <!-- Inline CSS -->
    <p style="color: red;">Teks ini akan berwarna MERAH karena Inline CSS memiliki prioritas tertinggi.</p>
</body>
</html>
4. Prioritas Selector: ID vs Class (#paragraf-1 vs .text-paragraf)
Pada elemen <p id="paragraf-1" class="text-paragraf">, jika masing-masing selector memiliki deklarasi CSS untuk properti yang sama, deklarasi pada ID Selector (#paragraf-1) yang akan ditampilkan pada browser.

Penjelasan:
Dalam aturan spesifisitas CSS, ID Selector (#) memiliki bobot yang jauh lebih tinggi dibandingkan Class Selector (.).

Nilai spesifisitas ID bernilai 1-0-0, sedangkan Class bernilai 0-1-0. Oleh karena itu, aturan pada ID selector akan selalu mengalahkan aturan pada Class selector.

Contoh Kode:
HTML
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>ID vs Class Selector</title>
    <style>
        /* Class Selector */
        .text-paragraf {
            color: blue;
            font-size: 14px;
        }

        /* ID Selector */
        #paragraf-1 {
            color: red; /* Warna ini yang akan menang dan diterapkan */
        }
    </style>
</head>
<body>
    <p id="paragraf-1" class="text-paragraf">Teks ini akan berwarna MERAH karena ID selector lebih kuat daripada Class selector.</p>
</body>
</html>
