# Facade Design Pattern

## 1. Penjelasan
Facade adalah salah satu design pattern yang menyediakan antarmuka sederhana untuk sekumpulan antarmuka dalam sebuah subsistem. Pattern ini membantu mengurangi kompleksitas dengan menyembunyikan detail implementasi dari klien.

## 2. Kapan Facade Digunakan?
Facade digunakan dalam kasus di mana sistem memiliki banyak subsistem yang kompleks dan ingin menyederhanakan akses ke fungsionalitas tersebut. Contohnya:
- Sistem manajemen perbankan
- Library multimedia (audio/video processing)
- API eksternal yang kompleks
- Framework yang memiliki banyak modul

## 3. Kelebihan dan Kekurangan

### Kelebihan:
- Menyederhanakan penggunaan sistem yang kompleks
- Mengurangi dependensi antara klien dan subsistem
- Mempermudah pemeliharaan dan perluasan sistem

### Kekurangan:
- Jika terlalu banyak fungsi ditambahkan ke Facade, bisa menyebabkan class menjadi terlalu besar
- Menambah lapisan tambahan yang bisa meningkatkan overhead jika tidak diimplementasikan dengan benar

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
