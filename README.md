# Flappy Bird Clone (.NET / WinForms)

![Language](https://img.shields.io/badge/Language-C%23-239120)
![Framework](https://img.shields.io/badge/.NET-Framework_4.8-512BD4)
![Status](https://img.shields.io/badge/Status-Stable-success)

A high-fidelity recreation of the classic Flappy Bird mechanism, built using **C# (Windows Forms)**.

Unlike standard WinForms applications that rely on default controls, this project utilizes **GDI+ graphics compositing** and **Optimized Double Buffering** to achieve smooth, flicker-free rendering at 60 FPS.

---

## 🎮 Features

* **Physics-Based Movement:** Implements custom velocity accumulation and gravity acceleration for "heavy" feeling flight mechanics.
* **Dynamic Difficulty:**
    * **Green Pipes:** Standard gap size.
    * **Red Pipes:** Randomized "Hard Mode" pipes (10% spawn rate) with tighter gaps and double points.
* **Smart Rendering:** Pipes are dynamically composited from sprite slices to prevent texture stretching on variable-height columns.
* **Asset Selection:** Choose your bird color (Yellow/Blue/Red) via a custom UI overlay before starting.
* **State Management:** Finite State Machine (FSM) handling Attract Mode (Idle), Gameplay, and Game Over states.

## 🛠️ Technical Highlights

### 1. GDI+ Sprite Compositing
To avoid the "stretched pixel" look common in WinForms games, I implemented a custom rendering pipeline. The `ComposePipeBitmap` function slices the source sprite, keeping the "Pipe Cap" aspect ratio locked while tiling the body 1px slice to fill the remaining height.

```csharp
// Logic from Form1.cs
private Bitmap ComposePipeBitmap(bool isHard, bool isTop, int targetWidth, int targetHeight)
{
    // Draws the cap (fixed height) and tiles the body (variable height)
    // to ensure high-quality visual scaling without distortion.
    // ...
}
```
### 2. Flicker Reduction

WinForms is notorious for screen flickering during rapid repaints. I overrode the CreateParams and enabled double-buffering to force the GPU/CPU to render the frame in memory before drawing it to the screen.
```csharp
this.SetStyle(
    ControlStyles.AllPaintingInWmPaint |
    ControlStyles.OptimizedDoubleBuffer |
    ControlStyles.UserPaint,
    true
);
```

## 🚀 How to Run
### Prerequisites

    Visual Studio 2019 or 2022

    .NET Framework 4.8

### Steps

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/TonyTheSlacker/flappybirdcsharp.git](https://github.com/TonyTheSlacker/flappybirdcsharp.git)

2. **Open flappy bird tesst.sln in Visual Studio.**

3. **Set the configuration to Release and press F5 to build and run.**
