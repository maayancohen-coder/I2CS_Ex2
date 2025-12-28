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

I2CS_Ex2/
├─ Ex2_GUI.java // GUI (StdDraw), menu, interaction, drawing, algorithm triggers
├─ Map2D.java // Interface
├─ Map.java // Implementation + algorithms (BFS fill, shortestPath, allDistance)
├─ Pixel2D.java // Pixel interface
├─ Index2D.java // Pixel implementation
├─ StdDraw.java // Provided drawing library
├─ MapTest.java // JUnit tests (including edge cases + Timeout)
├─ map.txt // Example map file (space-separated integers)
└─ images/
└─ gui.png // (optional) screenshot used in README

---

## ▶️ How to Run

1. Make sure all files are under the same package: `I2CS_Ex2`
2. Run:
   - `Ex2_GUI.main(...)`
3. Use the menu:
   - **Color** → choose pen color
   - **Draw** → select Line / Rectangle / Circle
   - **Algorithm** → Fill / Shortest Path / All Distance (if included in GUI)
   - **File** → Save / Load
   - **Edit** → Clear (if added)

---

## 🧠 Interaction Notes (Important)

- **Line / Rectangle / Circle** use **two clicks**:
  - first click selects `Pixel1`
  - second click selects `Pixel2` and draws
- Algorithms also use clicks:
  - **Fill**: click once to fill from that point
  - **Shortest Path**: click start, then click target
- The GUI refreshes after each operation using `changesMade`.

---

## 🧪 Testing

`MapTest.java` includes:
- Initialization tests
- Deep copy tests (`init`, `getMap`)
- Boundary/invalid input checks
- Drawing edge cases (single pixel line/rect/circle)
- BFS behavior (fill and shortest path)
- Performance check using `@Timeout`

Run tests with JUnit 5.

---

## ✅ Summary

This project demonstrates:
- clean separation between **GUI** and **logic**
- correct raster operations (line/rect/circle)
- BFS-based algorithms (fill, shortest path, distances)
- consistent mapping between **colors** and **integer values**

Enjoy drawing and solving mazes ✨

