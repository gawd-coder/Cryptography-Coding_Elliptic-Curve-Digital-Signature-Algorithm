# Cryptography-Coding_Elliptic-Curve-Digital-Signature-Algorithm
Fast elliptic curve cryptography, specifically digital signatures implemented using fastecdsa

# Elliptic Curve Cryptography

Written in mathematical terms, it is the set of all points (x,y) that fulfill the equation

y² = x³ +ax + b

Such a curve may then look like this for example:

<img width="451" alt="Screenshot 2021-10-01 at 10 56 35 AM" src="https://user-images.githubusercontent.com/57283161/135569938-b6144ec5-0049-40bf-a979-462797176b40.png">


You can also choose some point P on the curve and add it x-times to itself — you will still get a point located on the elliptic curve.

P+P+…+P = xP = R

In this case, x is just an arbitrary natural number. In elliptic curve cryptography one uses the fact that it is computationally infeasible to calculate the number x only by knowing the points P and R.

For cryptography, one chooses an appropriate point P on the elliptic curve generates a high enough random natural number x. This number is called the private key. With the chosen point P and the private key one calculates the point R on the curve, which is then defined as the public key. So public and private key are strongly connected to each other!

Signature = Sign(M,priv)    

where M be any message, pub by the public key and priv the private key of the sender.

In the above equation the function Sign() generates the signature. Anyone, who receives the message M can verify the signature — proving that the sender public key indeed also holds the private key:

Verify = Ver(Signature, M, pub)
