# 📘 Tugas 1 Pemrograman Berorientasi Object
### Meliputi materi :
1. **Class dan Object (Pertemuan 2)**
2. **Encapsulation (Pertemuan 3)**
3. **Constructor (Pertemuan 4)**


---

## 💻 Analisa Kode Berikut

### Kode `MakhlukHidup.java` dan `TestAccess.java` versi `ERROR`
><div style="color: blue">
><strong>Tugas:<br/>
>1. Temukan, jelaskan, dan perbaiki setiap error berkaitan dengan materi pada MakhlukHidup.java dan TestAccess.java. Ada 10+ kesalahan. Setiap kesalahan memiliki skor (lihat pada tabel skor). Skor minimal LULUS = 60.
><br/>
>2. Tuliskan output dari TestAccess jika kode sudah diperbaiki
></strong>
</div>

```java

public class MakhlukHidup {

    private string nama;       
    private String jenis;
    public double berat = -1.0;  
    private int umur;


    public MakhlukHidup() {
        this.nama = "Unknown";
        this.jenis = "Unknown";
        this.umur = 15;
        this.berat = 10.0;
    }

    public void MakhlukHidup(String nama) { 
        this.nama = nama;
        this.jenis = "Salah";
        this.umur = 12;
        this.berat = 170.0;
    }

    public makhlukHidup(String nama, String jenis, int umur, double berat) { 
        this.nama = jenis;  
        this.jenis = nama; 
        this.umur = umur;
        this.berat = berat;
    }

    public MakhlukHidup(MakhlukHidup other) {
        this.nama = nama; 
        this.jenis = other.jenis; 
        this.umur = this.umur; 
        this.berat = other.berat;
    }


    public void setUmur(String umur) { 
        this.umur = umur;
    }

    public void setNama(String nama) {
        nama = this.nama; 
    }

    public int getInfo() { 
        return "Nama=" + nama + ", Jenis=" + jenis 
        + ", Umur=" + umur + ", Berat=" + berat;
    }
}

```

```java
class TestAccess {
    public static void main(String[] args) {
        MakhlukHidup m = new MakhlukHidup();
        
        m.nama = "Kucing";  
        
        MakhlukHidup m2 = new MakhlukHidup("Harimau", "Hewan", 3, 120.0);
        
        MakhlukHidup m3 = new MakhlukHidup(m2);
 
        System.out.println(m.getInfo());
        
        System.out.println(m2.getInfo());
        
        m2.MakhlukHidup("Kuda"); 
                
        System.out.println(m2.getInfo());
        
        m3.setUmur(-10); 
        
        System.out.println(m3.getInfo());

        
    }
}
```


## Table Score
| No | Error | Materi terkait            | Skor |
|----|-------|---------------------------|------|
| 1  | ERR1  | Class & Object (syntax)   | 10   |
| 2  | ERR2  | Class & Object (type)     | 10   |
| 3  | ERR3  | Constructor/init          | 10   |
| 4  | ERR4  | Encapsulation / Setter    | 10   |
| 5  | ERR5  | Constructor (copy)        | 10   |
| 6  | ERR6  | Constructor (copy)        | 10   |
| 7  | ERR7  | Encapsulation / Setter    | 10   |
| 8  | ERR8  | Class & Object (type)     | 10   |
| 9  | ERR9  | Class & Object (type)     | 10   |
| 10 | ERR10 | Encapsulation / Validation| 10   |
**Total skor : 100**

## Petunjuk Pengerjaan

Temukan semua ERR#, jelaskan kenapa salah dalam bentuk table dengan kolom berikut, selanjutnya tulis kode perbaikannya.

| No | Class        | Kesalahan | Perbaikan |
|----|--------------|-----------|-----------|
| 1 | MakhlukHidup | [contoh] variable `jumlah` salah penulisan akses `publik` | seharusnya `public jumlah = 10`|

2. Kompilasi dan jalankan setelah diperbaiki.
3. Upload kode pada **Github** repository anda dan **upload link nya ke dalam sinau** di topik **Tugas 1 PBO** disertai **file penjelasannya** dalam format word atau markdown



#   JAWABAN
## 📋TABEL CLASS MAHLUKHIDUP DARI SOURCE CODE MakhlukHidup.java

|  No  |  Class        |  Kode Error |  Salah                                         |  Perbaikan                            | Penjelasan Sederhana                          |
|-----|--------------|------------|--------------------------------------------------------|--------------------------------------------|-----------------------------------------------|
| 1  | MakhlukHidup | ERR7       | `this.jenis = nama;` kebalik                          | Harusnya `this.jenis = jenis;`             | Atribut jenis salah isi, harus pakai jenis.   |
| 2   | MakhlukHidup | ERR7       | `nama = this.nama;` terbalik                          | Harusnya `this.nama = nama;`               | Urutan assignment salah.                      |
| 3   | MakhlukHidup | ERR2       | Nilai awal `berat = -1.0;`                            | Ganti ke `0.0`                             | Berat jangan negatif.                         |
| 4   | MakhlukHidup | ERR6       | `this.umur = this.umur;` ambil dirinya sendiri        | Harusnya `this.umur = other.umur;`         | Umur harus ambil dari objek lain.             |
| 5  | MakhlukHidup | ERR5       | `this.nama = nama;` salah ambil                      | Harusnya `this.nama = other.nama;`         | Nama harus ambil dari objek lain.             |
| 6   | MakhlukHidup | ERR8       | Constructor huruf kecil `makhlukHidup`                | Harus `MakhlukHidup`                       | Nama harus sama persis dengan class.          |
| 7   | MakhlukHidup | ERR1       | Pakai `string` huruf kecil                            | Harus `String`                             | Java butuh huruf besar.                       |
| 8  | MakhlukHidup | ERR9       | Setter umur pakai `String`                           | Ganti `setUmur(int umur)`                  | Umur harus angka, bukan teks.                 |
| 9   | MakhlukHidup | ERR10      | Getter info return `int` tapi balikin String          | Ubah ke `public String getInfo()`          | Fungsi balikin teks, bukan angka.             |
| 10   | MakhlukHidup | ERR9       | Setter umur beda tipe (String vs int)                 | Pakai `setUmur(int umur)`                  | Sama, umur itu angka.                         |
| 11   | MakhlukHidup | ERR3       | Constructor pakai `void`                              | Hilangkan `void`                           | Constructor gak boleh ada return type.        |
| 12   | MakhlukHidup | ERR10      | Getter info deklarasi `int`, isi String               | Deklarasi return `String`                  | Harus sesuai isi yang dikembalikan.           |
| 13  | MakhlukHidup | ERR4       | `this.nama = jenis;` kebalik                         | Harusnya `this.nama = nama;`               | Nama salah isi dengan jenis.                  |



## 📋TABEL CLASS MAHLUKHIDUP DARI SOURCE CODE MakhlukHidup.java

| No  | Class        | Kesalahan                                                                 | Perbaikan                                                                 |
|-----|--------------|---------------------------------------------------------------------------|---------------------------------------------------------------------------|
| 1   | TestAccess   | Tidak ada pemanggilan method `makan()` / `bergerak()` → aksi objek tidak berjalan (**ERR1**) | Tambahkan `m.makan(); m2.bergerak(); m2.makan(); m3.bergerak();` |
| 2   | TestAccess   | Konstruktor `("Harimau", "Hewan", 3, 120.0)` menggunakan jenis `"Hewan"` (**ERR2**) | Ganti `"Hewan"` menjadi `"Karnivora"` |
| 3   | TestAccess   | `m2.MakhlukHidup("Kuda");` dianggap memanggil konstruktor (**ERR3**) | Gunakan setter: `m2.setNama("Kuda"); m2.setJenis("Herbivora");` |
| 4   | TestAccess   | `m.nama = "Kucing";` langsung akses atribut private (**ERR4**) | Ganti dengan `m.setNama("Kucing");` |
| 5   | MakhlukHidup | Copy constructor salah: `this.berat = this.berat;` (**ERR5**) | Perbaiki: `this.berat = other.berat;` |
| 6   | MakhlukHidup | Copy constructor salah: `this.umur = this.umur;` (**ERR6**) | Perbaiki: `this.umur = other.umur;` |
| 7   | MakhlukHidup | Setter umur tidak validasi nilai negatif (**ERR7**) | Tambahkan validasi: `if(umur < 1) this.umur = 1; else this.umur = umur;` |
| 8   | TestAccess   | Jenis `"omnifora"` salah ketik (**ERR8**) | Benarkan jadi `"Omnivora"` |
| 9   | TestAccess   | Nama `Kuda` sudah diganti tapi jenis masih `"Karnivora"` (**ERR9**) | Tambahkan `m2.setJenis("Herbivora");` |
| 10  | MakhlukHidup | Setter berat tidak validasi nilai negatif (**ERR10**) | Tambahkan validasi: `if(berat < 0.1) this.berat = 0.1; else this.berat = berat;` |



###  💻SOURCE CODE MakhlukHidup.java YANG SUDAH DIPERBAIKI

```java
package MahlukHidup;
public class MakhlukHidup {

    // Atribut
    private String nama;
    private String jenis;
    private int umur;
    private double berat;

    // 1. Default Constructor
    public MakhlukHidup() {
        this.nama = "kucing";
        this.jenis = "Omnifora";
        this.umur = 1;   // umur minimal 1
        this.berat = 0.1; // berat minimal 0.1
        System.out.println("[Default Constructor] Objek MakhlukHidup dibuat.");
    }

    // 2. Parameterized Constructor
    public MakhlukHidup(String nama, String jenis, int umur, double berat) {
        this.nama = nama;
        this.jenis = jenis;
        this.umur = (umur > 0) ? umur : 1;
        this.berat = (berat > 0) ? berat : 0.1;
        System.out.println("[Parameterized Constructor] Objek MakhlukHidup dibuat.");
    }

    // 3. Copy Constructor
    public MakhlukHidup(MakhlukHidup other) {
        this.nama = other.nama;
        this.jenis = other.jenis;
        this.umur = (other.umur > 0) ? other.umur : 1;
        this.berat = (other.berat > 0) ? other.berat : 0.1;
        System.out.println("[Copy Constructor] Objek MakhlukHidup disalin.");
    }

    // Setter
    public void setNama(String nama) {
        this.nama = nama;
    }

    public void setJenis(String jenis) {
        this.jenis = jenis;
    }

    public void setUmur(int umur) {
        this.umur = (umur > 0) ? umur : 1;
    }

    public void setBerat(double berat) {
        this.berat = (berat > 0) ? berat : 0.1;
    }

    // Getter
    public String getNama() {
        return nama;
    }

    public String getJenis() {
        return jenis;
    }

    public int getUmur() {
        return umur;
    }

    public double getBerat() {
        return berat;
    }

    public String getInfo() {
        return "Nama: " + nama + ", Jenis: " + jenis + ", Umur: " + umur + ", Berat: " + berat;
    }

    // Method 
    public void makan() {
        System.out.println(nama + " sedang makan.");
    }

    public void bergerak() {
        System.out.println(nama + " sedang bergerak.");
    }

    @Override
    public String toString() {
        return "MakhlukHidup {nama='" + nama + "', jenis='" + jenis + "', umur=" + umur + ", berat=" + berat + "}";
    }
}

```


###  💻SOURCE CODE TestAccesc.java YANG SUDAH DIPERBAIKI

```jav
package MahlukHidup;

class TestAccess {
    public static void main(String[] args) {
        MakhlukHidup m = new MakhlukHidup();
        m.setNama("Kucing");  
        m.setJenis("Omnivora");

        MakhlukHidup m2 = new MakhlukHidup("Harimau", "Karnivora", 3, 120.0);
        MakhlukHidup m3 = new MakhlukHidup(m2);

        // Kucing → makan
        System.out.println(m.getInfo());
        m.makan();

        // Harimau → bergerak
        System.out.println(m2.getInfo());
        m2.bergerak();

        // Kuda → makan
        m2.setNama("Kuda"); 
        m2.setJenis("Herbivora");
        System.out.println(m2.getInfo());
        m2.makan();

        // Salinan Harimau → bergerak
        m3.setUmur(-10);   // otomatis jadi 1
        m3.setBerat(-50);  // otomatis jadi 0.1
        System.out.println(m3.getInfo());
        m3.bergerak();
    }
}



```

### 📋OUTPUT CODE TestAccesc

```
[Default Constructor] Objek MakhlukHidup dibuat.
[Parameterized Constructor] Objek MakhlukHidup dibuat.
[Copy Constructor] Objek MakhlukHidup disalin.
Nama: Kucing, Jenis: Omnivora, Umur: 1, Berat: 0.1
Kucing sedang makan.
Nama: Harimau, Jenis: Karnivora, Umur: 3, Berat: 120.0
Harimau sedang bergerak.
Nama: Kuda, Jenis: Herbivora, Umur: 3, Berat: 120.0
Kuda sedang makan.
Nama: Harimau, Jenis: Karnivora, Umur: 1, Berat: 0.1
Harimau sedang bergerak.
PS C:\Users\HP\Documents\GitHub\belajar-githb> 
```
