# DFT_By_Correlation
Here’s the content formatted in a way that you can easily copy and paste into a document:

---

### **DFT by Correlation**

The DFT can be computed by correlating the input signal \( x[i] \) with sine and cosine functions at different frequencies. This approach separates the DFT into its **real** and **imaginary** parts.

---

### **Formulas**

1. **Real Part of DFT (\( ReX[k] \))**:
   \[
   ReX[k] = \sum_{i=0}^{N-1} x[i] \cdot \cos\left(\frac{2\pi k i}{N}\right)
   \]
   - This computes the correlation between the signal \( x[i] \) and a cosine wave of frequency \( \frac{2\pi k}{N} \).

2. **Imaginary Part of DFT (\( ImX[k] \))**:
   \[
   ImX[k] = -\sum_{i=0}^{N-1} x[i] \cdot \sin\left(\frac{2\pi k i}{N}\right)
   \]
   - This computes the correlation between the signal \( x[i] \) and a sine wave of frequency \( \frac{2\pi k}{N} \).

---

### **Explanation**

1. **Correlation with Cosine**:
   - The real part \( ReX[k] \) measures how much the signal \( x[i] \) "matches" a cosine wave at frequency \( \frac{2\pi k}{N} \).
   - If the signal has a strong cosine component at this frequency, \( ReX[k] \) will be large.

2. **Correlation with Sine**:
   - The imaginary part \( ImX[k] \) measures how much the signal \( x[i] \) "matches" a sine wave at frequency \( \frac{2\pi k}{N} \).
   - If the signal has a strong sine component at this frequency, \( ImX[k] \) will be large.

3. **Combining Real and Imaginary Parts**:
   - The full DFT \( X[k] \) is a complex number formed by combining the real and imaginary parts:
     \[
     X[k] = ReX[k] + j \cdot ImX[k]
     \]
   - The **magnitude** of \( X[k] \) represents the strength of the frequency component \( k \), and the **phase** represents the timing offset of the component.

---

### **Example**

Let’s compute the DFT of a simple signal using the correlation approach.

#### **Input Signal**

Consider a signal \( x[i] \) of length \( N = 4 \):
\[
x[0] = 1, \quad x[1] = 2, \quad x[2] = 3, \quad x[3] = 4
\]

---

#### **Step 1: Compute \( ReX[k] \) and \( ImX[k] \) for \( k = 0 \)**

For \( k = 0 \):
- \( \cos(0) = 1 \), \( \sin(0) = 0 \)
- \( ReX[0] = 1 \cdot 1 + 2 \cdot 1 + 3 \cdot 1 + 4 \cdot 1 = 10 \)
- \( ImX[0] = - (1 \cdot 0 + 2 \cdot 0 + 3 \cdot 0 + 4 \cdot 0) = 0 \)

So, \( X[0] = 10 + j \cdot 0 = 10 \).

---

#### **Step 2: Compute \( ReX[k] \) and \( ImX[k] \) for \( k = 1 \)**

For \( k = 1 \):
- \( \cos\left(\frac{2\pi \cdot 1 \cdot i}{4}\right) = \cos\left(\frac{\pi i}{2}\right) \)
- \( \sin\left(\frac{2\pi \cdot 1 \cdot i}{4}\right) = \sin\left(\frac{\pi i}{2}\right) \)

Compute each term:
- For \( i = 0 \): \( \cos(0) = 1 \), \( \sin(0) = 0 \)
- For \( i = 1 \): \( \cos\left(\frac{\pi}{2}\right) = 0 \), \( \sin\left(\frac{\pi}{2}\right) = 1 \)
- For \( i = 2 \): \( \cos(\pi) = -1 \), \( \sin(\pi) = 0 \)
- For \( i = 3 \): \( \cos\left(\frac{3\pi}{2}\right) = 0 \), \( \sin\left(\frac{3\pi}{2}\right) = -1 \)

Now compute \( ReX[1] \) and \( ImX[1] \):
\[
ReX[1] = 1 \cdot 1 + 2 \cdot 0 + 3 \cdot (-1) + 4 \cdot 0 = 1 - 3 = -2
\]
\[
ImX[1] = - (1 \cdot 0 + 2 \cdot 1 + 3 \cdot 0 + 4 \cdot (-1)) = - (2 - 4) = 2
\]

So, \( X[1] = -2 + j \cdot 2 \).

---

#### **Step 3: Repeat for \( k = 2 \) and \( k = 3 \)**

You can follow the same process to compute \( X[2] \) and \( X[3] \).

---

### **Summary**

- The DFT can be computed by correlating the signal with sine and cosine waves at different frequencies.
- The real part \( ReX[k] \) measures the cosine component, and the imaginary part \( ImX[k] \) measures the sine component.
- Combining these gives the full DFT \( X[k] \), which represents the frequency content of the signal.

---

This format should work well for copying into a document. Let me know if you need further adjustments!
