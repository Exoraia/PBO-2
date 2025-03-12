# Facade Design Pattern

## 1. Penjelasan
Pola Desain Facade adalah pola desain struktural yang menyediakan antarmuka yang disederhanakan ke sekumpulan antarmuka dalam subsistem sehingga lebih mudah digunakan. Pola ini melibatkan pembuatan kelas facade yang merepresentasikan antarmuka tingkat tinggi dan terpadu ke sekumpulan antarmuka dalam subsistem. Pola ini menyembunyikan kompleksitas subsistem dan menyediakan antarmuka yang lebih sederhana untuk kode klien.

Sumber: https://belatrix.globant.com/us-en/blog/tech-trends/facade-design-pattern/

Facade simplenya adalah gateway sederhana yang menuju ke penggunaan fungsi yang kompleks. Sedangkan Proxy menyediakan interface yang sama dengan kelas yang diproksikan dan biasanya melakukan beberapa hal seperti housekeeping stuff. Jadi dari pada membuat beberapa copy-an dari sebuah heavy object X, kita dapar membuat salinan proxy yang ringan yang pada gilirannya mengelola X dan menerjemahkan panggilan kita sebagaimana diperlukan.

Sumber: https://stackoverflow.com/questions/3489131/difference-between-the-facade-proxy-adapter-and-decorator-design-patterns

## 2. Kapan Facade Digunakan?
Pattern Facade digunakan untuk menyederhanakan kompleksitas sistem dengan menyediakan interface yang mudah digunakan, sehingga pengguna tidak perlu berurusan dengan detail implementasi yang rumit di balik interface tersebut. 

Contoh kasus :
Bayangkan Anda ingin mengontrol berbagai perangkat smart home (TV, AC, lampu, dll). Dengan Facade, Anda cukup berinteraksi dengan Facade untuk menyalakan TV, mengatur AC, dan mematikan lampu, tanpa harus memahami bagaimana setiap perangkat bekerja. 
Jadi, Cara kerja facade ini dapat disimpulkan bahwa kita dapat mengetahui fungsi kerja suatu fitur tanpa kita harus mengetahui detail dari fitur tersebut

Sumber: https://ferry.vercel.app/blog/contoh-facade-design-pattern#:~:text=Fa%C3%A7ade%20Design%20Pattern%20cocok%20digunakan,juga%20bisa%20menjadi%20God%20Object.

## 3. Kelebihan dan Kekurangan

### Kelebihan:
- Antarmuka yang Disederhanakan:
Keuntungan utama dari pola Facade adalah penyediaan antarmuka yang disederhanakan bagi klien

- Enkapsulasi Kompleksitas
Pola Facade merangkum interaksi dan ketergantungan kompleks subsistem dalam satu komponen.

- Peningkatan Kemudahan Pemeliharaan
Pola Facade meningkatkan kemudahan pemeliharaan kode dengan menyediakan titik terpusat untuk mengelola interaksi dengan subsistem.

### Kekurangan:
- Fleksibilitas Terbatas
Salah satu potensi kerugian dari pola Facade adalah dapat membatasi fleksibilitas dalam beberapa kasus. Karena Facade menyediakan antarmuka yang disederhanakan, mungkin tidak akan menampilkan semua fungsi atau opsi penyesuaian yang tersedia di subsistem yang mendasarinya.

- Meningkatnya Ketergantungan pada Façade
Facade menimbulkan ketergantungan antara klien dan komponen Facade. Klien menjadi sangat terikat dengan Facade, dan setiap perubahan atau pembaruan pada Facade dapat memengaruhi kode klien.

- Ekstensibilitas Terbatas
Pola Facade mungkin menghadapi keterbatasan saat memperluas sistem dengan subsistem atau fungsi baru. Penambahan subsistem baru mungkin memerlukan modifikasi pada Facade, yang berpotensi memengaruhi kode klien yang ada.

Sumber: https://dotnettutorials.net/lesson/facade-design-pattern-in-java/

## 4. Contoh Kode dalam Java
```java
// CPU
class CPU {
    void start() {
        System.out.println("CPU started");
    }
}

// Memory
class Memory {
    void load() {
        System.out.println("Memory loaded");
    }
}

// HardDrive
class HardDrive {
    void read() {
        System.out.println("Hard Drive reading data");
    }
}

// Facade
class Computer {
    private CPU cpu;
    private Memory memory;
    private HardDrive hardDrive;
    
    public Computer() {
        this.cpu = new CPU();
        this.memory = new Memory();
        this.hardDrive = new HardDrive();
    }
    
    public void startComputer() {
        cpu.start();
        memory.load();
        hardDrive.read();
        System.out.println("Computer started successfully");
    }
}

// Main Class
public class Main {
    public static void main(String[] args) {
        Computer computer = new Computer();
        computer.startComputer();
    }
}
```

## 5. Output yang Dihasilkan
```
CPU started
Memory loaded
Hard Drive reading data
Computer started successfully
```
