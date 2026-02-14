# PANDUAN LENGKAP
## Game Edukasi Matematika - Java Version

### Informasi Mahasiswa
- **Nama**: Ahmad Husnul Fudoli
- **Tanggal**: 14 Februari 2026

---

## 🎯 APA YANG SUDAH DIBUAT?

### 1. **Project Java Lengkap** ✅
- **File**: GameEdukasiMatematika.zip
- **Bahasa**: Java (NetBeans ready)
- **Framework**: Java Swing GUI
- **Pattern**: MVC (Model-View-Controller)

### 2. **Struktur Lengkap**
```
GameEdukasiMatematika/
├── src/
│   ├── Main.java              # Entry point
│   ├── model/                 # Data models
│   │   ├── Player.java
│   │   ├── Question.java
│   │   └── Difficulty.java
│   ├── controller/            # Business logic
│   │   └── GameController.java
│   ├── view/                  # GUI
│   │   ├── MainFrame.java
│   │   ├── StartPanel.java
│   │   ├── GamePanel.java
│   │   ├── ResultPanel.java
│   │   └── LeaderboardPanel.java
│   └── util/                  # Utilities
│       ├── QuestionGenerator.java
│       └── FileManager.java
└── data/
    └── leaderboard.dat
```

---

## 📚 KONSEP OOP YANG DITERAPKAN

### 1. **Encapsulation** (Enkapsulasi)
- Semua atribut private
- Akses via getter/setter
- **Contoh**: 
```java
public class Player {
    private String name;  // Private attribute
    
    public String getName() {  // Public getter
        return name;
    }
}
```

### 2. **Inheritance** (Pewarisan)
- Panel extends JPanel
- **Contoh**: `StartPanel extends JPanel`

### 3. **Polymorphism** (Polimorfisme)
- Method overriding: `toString()`, `compareTo()`
- **Contoh**:
```java
@Override
public String toString() {
    return questionText;
}
```

### 4. **Abstraction** (Abstraksi)
- Enum Difficulty
- Interface: Serializable, Comparable
- **Contoh**: `Difficulty.MUDAH.getMaxNumber()`

---

## 🚀 CARA MENJALANKAN

### Di NetBeans:
1. Extract file `GameEdukasiMatematika.zip`
2. Buka NetBeans
3. File → Open Project
4. Pilih folder GameEdukasiMatematika
5. Klik kanan project → Run
6. **DONE!** ✅

### Manual (Terminal):
```bash
# 1. Extract zip file
unzip GameEdukasiMatematika.zip

# 2. Compile
cd GameEdukasiMatematika
javac -d bin src/**/*.java src/*.java

# 3. Run
java -cp bin src.Main
```

---

## ✨ FITUR APLIKASI

### 1. **Multiple Difficulty Levels**
- Mudah: 1-10, 30 detik
- Sedang: 1-50, 25 detik
- Sulit: 1-100, 20 detik

### 2. **Operasi Matematika**
- Penjumlahan (+)
- Pengurangan (-)
- Perkalian (×)

### 3. **Sistem Scoring**
- 10 soal per game
- 10 poin per jawaban benar
- Max 100 poin

### 4. **Timer Countdown**
- Real-time countdown
- Game otomatis berakhir saat waktu habis

### 5. **Leaderboard**
- Top 10 players
- Data tersimpan permanen (Serialization)
- Sorting otomatis by score

### 6. **File Persistence**
- Serialization untuk save Player objects
- FileManager utility class
- Data tetap ada setelah aplikasi ditutup

---

## 🎨 GUI COMPONENTS

### Start Screen
- 3 tombol difficulty (Mudah, Sedang, Sulit)
- 1 tombol leaderboard
- Design colorful dengan gradient

### Game Screen
- Label skor (top left)
- Label timer (top right)
- Card soal di tengah
- Text field untuk input jawaban
- Button submit
- Label feedback (benar/salah)

### Result Screen
- Label judul "Permainan Selesai"
- Skor final (besar)
- Pesan motivasi
- Input nama pemain
- 3 tombol: Save, Main Lagi, Leaderboard

### Leaderboard Screen
- Table dengan 5 kolom
- Medal emoji untuk top 3
- Color coding (Gold, Silver, Bronze)
- Button back

---

## 💾 FILE I/O & PERSISTENCE

### Serialization
```java
// Save to file
try (ObjectOutputStream oos = 
     new ObjectOutputStream(new FileOutputStream("data.dat"))) {
    oos.writeObject(players);
}

// Load from file
try (ObjectInputStream ois = 
     new ObjectInputStream(new FileInputStream("data.dat"))) {
    players = (List<Player>) ois.readObject();
}
```

### File Manager Features
- `savePlayer(Player)` - Save single player
- `loadLeaderboard()` - Load all players
- `clearLeaderboard()` - Clear data (testing)

---

## 🎯 CLASS DIAGRAM (Simplified)

```
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│   Main      │─────▶│  MainFrame   │◆────▶│  *Panel     │
└─────────────┘      └──────────────┘      └─────────────┘
                                                   │
                            ┌──────────────────────┼────────────┐
                            │                      │            │
                     ┌──────▼──────┐      ┌───────▼─────┐  ┌──▼────┐
                     │ StartPanel  │      │  GamePanel  │  │ Result│
                     └─────────────┘      └─────────────┘  └───────┘
                                                  │
                                          ┌───────▼────────┐
                                          │GameController  │
                                          └────────────────┘
                                                  │
                          ┌───────────────────────┼───────────────┐
                          │                       │               │
                    ┌─────▼─────┐        ┌────────▼──────┐  ┌────▼─────┐
                    │  Question │        │ QuestionGen   │  │  Player  │
                    └───────────┘        └───────────────┘  └──────────┘
```

---

## 📋 CHECKLIST UNTUK UAS

### ✅ Yang Sudah Selesai:
- [x] Project Java lengkap dengan OOP
- [x] Implementasi Encapsulation
- [x] Implementasi Inheritance
- [x] Implementasi Polymorphism
- [x] Implementasi Abstraction
- [x] GUI dengan Java Swing
- [x] File I/O & Serialization
- [x] README.md documentation
- [x] Source code lengkap
- [x] ZIP file ready

### 📝 Yang Perlu Dilakukan:
1. Extract file ZIP
2. Buka di NetBeans
3. Test run aplikasi
4. Screenshot untuk dokumentasi
5. Upload ke GitHub
6. Buat laporan/ebook (opsional)

---

## 🔍 TESTING CHECKLIST

### Functional Testing:
- [ ] Aplikasi bisa dijalankan tanpa error
- [ ] Pilih difficulty → Game dimulai
- [ ] Input jawaban → Validasi benar
- [ ] Timer countdown → Berjalan normal
- [ ] Game selesai → Tampil result
- [ ] Save score → Tersimpan di leaderboard
- [ ] Leaderboard → Tampil data benar
- [ ] Sorting → Top score di atas

### Non-Functional Testing:
- [ ] GUI responsive
- [ ] Colors menarik
- [ ] Fonts readable
- [ ] Buttons clickable
- [ ] Input validation works

---

## 🎓 PENJELASAN UNTUK DOSEN

### Konsep PBO yang Digunakan:

1. **Encapsulation**: 
   - Semua class menggunakan private attributes
   - Public methods untuk access control
   - Data hiding dan security

2. **Inheritance**:
   - Semua Panel extend dari JPanel
   - Reuse code dari parent class
   - Polymorphic behavior

3. **Polymorphism**:
   - Method overriding (toString, compareTo)
   - Interface implementation
   - Multiple forms dari same method

4. **Abstraction**:
   - Enum Difficulty untuk abstraksi levels
   - Interface Serializable, Comparable
   - Utility classes (static methods)

### Design Pattern:
- **MVC Pattern**: Model-View-Controller
  - Model: Player, Question, Difficulty
  - View: All Panel classes
  - Controller: GameController

### File I/O:
- **Serialization**: Object → File
- **Deserialization**: File → Object
- **Persistence**: Data saved permanently

---

## 📞 CONTACT

Ahmad Husnul Fudoli
NIM: 24131310006

---

**© 2026 - Game Edukasi Matematika (Java Version)**
