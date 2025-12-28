# I2CS_Ex2
# Ex2 — Map2D GUI + Algorithms (StdDraw)

Interactive 2D grid editor and algorithm playground for **Intro2CS 2026A**.  
Draw shapes on a raster map, run BFS-based algorithms, and save/load maps from file.

**Author:** Maayan Cohen

---

## 🖼️ Screenshot

<img width="629" height="697" alt="image" src="https://github.com/user-attachments/assets/357ecc4f-e785-4cb4-823a-b49441dd30ef" />


---

## ✨ Features

### 🎨 Drawing (GUI)
- Choose a color from the menu
- Draw:
  - Line (two clicks)
  - Rectangle (two clicks)
  - Circle (center + radius click)

### 🧠 Algorithms (Map logic)
- **Flood Fill (BFS)**
- **Shortest Path (BFS)**
- **All Distance Map (BFS distances)**

### 💾 File Support
- Load map from text file
- Save current map to file
- Clear the entire map

---

## 🎯 Color & Value Convention

The map stores **integers**, while the GUI displays them as colors.  
Algorithms use **values**, not Java `Color`.

| Color     | Value | Meaning |
|----------:|:-----:|--------|
| Black     | 0     | Empty / background |
| Magenta  | 1     | Free cell |
| **Red**  | **2** | **Obstacle (blocked)** |
| Yellow   | 3     | Free cell |

- `obsColor = 2` means: any cell with value **2** is treated as an obstacle.
- GUI uses `penValue` to write values into the map.

---

## 🧩 Project Structure

