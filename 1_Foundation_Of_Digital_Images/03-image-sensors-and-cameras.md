# 03-image-sensors-and-cameras.md

## **1. Introduction**
Image sensors are the core components that convert light into digital signals. Cameras combine lenses, sensors, and electronics to form complete imaging systems. Understanding how sensors and cameras work is crucial for image processing, computer vision, and photography.

This file covers:
- Types of image sensors  
- Pixel architecture  
- Color filter arrays  
- Camera types  
- Important imaging parameters  

---

## **2. What Is an Image Sensor?**
An **image sensor** converts incoming photons into electrical charges that are digitized to form a digital image.

Two major sensor families dominate the industry:

1. **CCD (Charge-Coupled Device)**
2. **CMOS (Complementary Metal-Oxide Semiconductor)**

---

## **3. CCD vs. CMOS**
### **CCD Sensors**
- Charges are transferred across the chip and read at one corner.
- High-quality images, low noise.
- Higher power consumption.
- Used in astronomy and scientific imaging.

### **CMOS Sensors**
- Each pixel has its own amplifier + ADC.
- Lower cost, lower power.
- Faster readout.
- Used in phones, DSLRs, webcams.

### **Key Differences Table**

| Feature | CCD | CMOS |
|--------|-----|------|
| Readout | Serial | Parallel |
| Noise | Low | Moderate |
| Speed | Slow | Fast |
| Power | High | Low |
| Cost | High | Low |

---

## **4. Pixel Architecture**
Each pixel typically contains:
- **Photodiode** – converts light to electrons  
- **Microlens** – collects more light  
- **Color filter** – defines R, G, B  

### **Pixel Equation**
Number of electrons generated:

\[
N_e = P \cdot QE
\]

Where:  
- \(P\) = photon count  
- \(QE\) = quantum efficiency  

---

## **5. Color Filter Arrays (CFA)**
Most sensors capture only **brightness**, not color.  
Color is reconstructed using **Color Filter Arrays**.

### **Bayer Pattern (Most Common)**

```
G R
B G
```

- 50% Green (mimics human eye)
- 25% Red
- 25% Blue

### **Demosaicing**
Process of reconstructing full RGB values from CFA data.

---

## **6. Global vs. Rolling Shutter**
### **Rolling Shutter**
- Exposes lines sequentially  
- Causes distortions during motion  

### **Global Shutter**
- Exposes all pixels simultaneously  
- Used in robotics, machine vision, AR/VR  

---

## **7. Camera Lenses**
A camera lens focuses light onto the sensor.

Key properties:
- **Focal length (f)**  
- **Aperture (f-number)**  
- **Depth of field**  
- **Optical distortion**  

### **Thin Lens Equation**
\[
\frac{1}{f} = \frac{1}{d_o} + \frac{1}{d_i}
\]

---

## **8. Types of Cameras**
### **1. Smartphone Cameras**
- Tiny sensors, multi-lens systems
- Computational photography

### **2. DSLR / Mirrorless Cameras**
- Large sensors → high quality  
- Interchangeable lenses  

### **3. Industrial Cameras**
- Global shutter  
- High frame rate  

### **4. Scientific Cameras**
- Cooled sensors  
- High dynamic range  

### **5. Stereo & Depth Cameras**
- LiDAR  
- Time-of-flight  
- Structured light  

---

## **9. Important Camera Parameters**
### **Dynamic Range**
\[
DR = 20 \log_{10} \left(\frac{I_{max}}{I_{min}}\right)
\]

### **Signal-to-Noise Ratio (SNR)**
\[
SNR = \frac{Signal}{Noise}
\]

### **Quantum Efficiency**
Probability that a photon generates an electron.

### **Full Well Capacity**
Maximum electrons a pixel can store.

---

## **10. Camera Calibration**
Used to correct:
- Distortion  
- Intrinsic parameters  
- Extrinsic parameters  

Projection matrix:

\[
    s\begin{bmatrix} x \\ y \\ 1 \end{bmatrix}
    =
K [ R \mid t ] 
\begin{bmatrix} X \\ Y \\ Z \\ 1 \end{bmatrix}
\]

Where:  
- \(K\) = intrinsic matrix  
- \(R,t\) = rotation and translation  

---

## **11. Real-World Example (Conceptual)**
1. Light hits the lens  
2. Lens focuses it onto sensor  
3. Photodiodes convert light to electrons  
4. ADC converts electrons to pixel values  
5. ISP (Image Signal Processor) performs sharpening, denoising, demosaicing  

---

## **12. Best Practices**
- Use RAW format when accuracy matters  
- Avoid high ISO unless necessary  
- Calibrate your camera for scientific work  
- Prefer global shutter for fast motion scenes  

---

## **13. References**
- Szeliski – Computer Vision  
- Burger & Burge – Digital Image Processing  
- OpenCV: Camera Calibration Tutorials  
