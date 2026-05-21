# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM (DIRECT) : 
// DISCRETE FOURIER TRANSFORM 
```
clc; 
clear; 
xn=[1 2 3 4 4 3 2 1]; 
 
n1=0:1:length(xn)-1; 
subplot(3,1,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude xn'); 
title('Input Sequence'); 
j=sqrt(-1); 
N=length(xn); 
Xk=zeros(1,N); 
for k=0:N-1 
for n=0:N-1 
Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N); 
end   
end 
disp(Xk) 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(3,1,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(3,1,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum'); 
```
# PROGRAM (FFT) :
```
clear; 
clc; 
close; 
xn = [0.5 0.5 0.5 0.5 0 0 0 0] 
 
n1=0:1:length(xn)-1; 
subplot(2,2,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Input Sequence'); 
 
Xk = fft(xn); 
 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(2,2,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(2,2,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum') 
y= ifft(Xk) 
 
n2=0:1:length(y)-1; 
subplot(2,2,4) 
plot2d3(n2,y) 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Inverse FFT OF X(K)');
```

# OUTPUT (DIRECT) : 
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/480bd178-6f11-42df-9b34-d930099b313f" />

# OUTPUT (FFT) :
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/c6a784de-5cca-4a14-a048-a5ed9c169e7d" />

# RESULT: 
Thus,The DFT and FFT of the given sequence is obtained using SCILAB.
