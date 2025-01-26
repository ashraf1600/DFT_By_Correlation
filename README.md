DFT by Correlation
The DFT can be computed by correlating the input signal 
x
[
i
]
x[i] with sine and cosine functions at different frequencies. This approach separates the DFT into its real and imaginary parts.

Formulas
Real Part of DFT (
R
e
X
[
k
]
ReX[k]):

R
e
X
[
k
]
=
∑
i
=
0
N
−
1
x
[
i
]
⋅
cos
⁡
(
2
π
k
i
N
)
ReX[k]= 
i=0
∑
N−1
​
 x[i]⋅cos( 
N
2πki
​
 )
This computes the correlation between the signal 
x
[
i
]
x[i] and a cosine wave of frequency 
2
π
k
N
N
2πk
​
 .

Imaginary Part of DFT (
I
m
X
[
k
]
ImX[k]):

I
m
X
[
k
]
=
−
∑
i
=
0
N
−
1
x
[
i
]
⋅
sin
⁡
(
2
π
k
i
N
)
ImX[k]=− 
i=0
∑
N−1
​
 x[i]⋅sin( 
N
2πki
​
 )
This computes the correlation between the signal 
x
[
i
]
x[i] and a sine wave of frequency 
2
π
k
N
N
2πk
​
 .

Explanation
Correlation with Cosine:

The real part 
R
e
X
[
k
]
ReX[k] measures how much the signal 
x
[
i
]
x[i] "matches" a cosine wave at frequency 
2
π
k
N
N
2πk
​
 .

If the signal has a strong cosine component at this frequency, 
R
e
X
[
k
]
ReX[k] will be large.

Correlation with Sine:

The imaginary part 
I
m
X
[
k
]
ImX[k] measures how much the signal 
x
[
i
]
x[i] "matches" a sine wave at frequency 
2
π
k
N
N
2πk
​
 .

If the signal has a strong sine component at this frequency, 
I
m
X
[
k
]
ImX[k] will be large.

Combining Real and Imaginary Parts:

The full DFT 
X
[
k
]
X[k] is a complex number formed by combining the real and imaginary parts:

X
[
k
]
=
R
e
X
[
k
]
+
j
⋅
I
m
X
[
k
]
X[k]=ReX[k]+j⋅ImX[k]
The magnitude of 
X
[
k
]
X[k] represents the strength of the frequency component 
k
k, and the phase represents the timing offset of the component.

Example
Let’s compute the DFT of a simple signal using the correlation approach.

Input Signal
Consider a signal 
x
[
i
]
x[i] of length 
N
=
4
N=4:

x
[
0
]
=
1
,
x
[
1
]
=
2
,
x
[
2
]
=
3
,
x
[
3
]
=
4
x[0]=1,x[1]=2,x[2]=3,x[3]=4
Step 1: Compute 
R
e
X
[
k
]
ReX[k] and 
I
m
X
[
k
]
ImX[k] for 
k
=
0
k=0
For 
k
=
0
k=0:

cos
⁡
(
0
)
=
1
cos(0)=1, 
sin
⁡
(
0
)
=
0
sin(0)=0

R
e
X
[
0
]
=
1
⋅
1
+
2
⋅
1
+
3
⋅
1
+
4
⋅
1
=
10
ReX[0]=1⋅1+2⋅1+3⋅1+4⋅1=10

I
m
X
[
0
]
=
−
(
1
⋅
0
+
2
⋅
0
+
3
⋅
0
+
4
⋅
0
)
=
0
ImX[0]=−(1⋅0+2⋅0+3⋅0+4⋅0)=0

So, 
X
[
0
]
=
10
+
j
⋅
0
=
10
X[0]=10+j⋅0=10.

Step 2: Compute 
R
e
X
[
k
]
ReX[k] and 
I
m
X
[
k
]
ImX[k] for 
k
=
1
k=1
For 
k
=
1
k=1:

cos
⁡
(
2
π
⋅
1
⋅
i
4
)
=
cos
⁡
(
π
i
2
)
cos( 
4
2π⋅1⋅i
​
 )=cos( 
2
πi
​
 )

sin
⁡
(
2
π
⋅
1
⋅
i
4
)
=
sin
⁡
(
π
i
2
)
sin( 
4
2π⋅1⋅i
​
 )=sin( 
2
πi
​
 )

Compute each term:

For 
i
=
0
i=0: 
cos
⁡
(
0
)
=
1
cos(0)=1, 
sin
⁡
(
0
)
=
0
sin(0)=0

For 
i
=
1
i=1: 
cos
⁡
(
π
2
)
=
0
cos( 
2
π
​
 )=0, 
sin
⁡
(
π
2
)
=
1
sin( 
2
π
​
 )=1

For 
i
=
2
i=2: 
cos
⁡
(
π
)
=
−
1
cos(π)=−1, 
sin
⁡
(
π
)
=
0
sin(π)=0

For 
i
=
3
i=3: 
cos
⁡
(
3
π
2
)
=
0
cos( 
2
3π
​
 )=0, 
sin
⁡
(
3
π
2
)
=
−
1
sin( 
2
3π
​
 )=−1

Now compute 
R
e
X
[
1
]
ReX[1] and 
I
m
X
[
1
]
ImX[1]:

R
e
X
[
1
]
=
1
⋅
1
+
2
⋅
0
+
3
⋅
(
−
1
)
+
4
⋅
0
=
1
−
3
=
−
2
ReX[1]=1⋅1+2⋅0+3⋅(−1)+4⋅0=1−3=−2
I
m
X
[
1
]
=
−
(
1
⋅
0
+
2
⋅
1
+
3
⋅
0
+
4
⋅
(
−
1
)
)
=
−
(
2
−
4
)
=
2
ImX[1]=−(1⋅0+2⋅1+3⋅0+4⋅(−1))=−(2−4)=2
So, 
X
[
1
]
=
−
2
+
j
⋅
2
X[1]=−2+j⋅2.

Step 3: Repeat for 
k
=
2
k=2 and 
k
=
3
k=3
You can follow the same process to compute 
X
[
2
]
X[2] and 
X
[
3
]
X[3].

Summary
The DFT can be computed by correlating the signal with sine and cosine waves at different frequencies.

The real part 
R
e
X
[
k
]
ReX[k] measures the cosine component, and the imaginary part 
I
m
X
[
k
]
ImX[k] measures the sine component.

Combining these gives the full DFT 
X
[
k
]
X[k], which represents the frequency content of the signal.
