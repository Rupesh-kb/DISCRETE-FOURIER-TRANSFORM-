# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

## AIM: 

To Obtain DFT and FFT of a given sequence in SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
```scilab
clc;
clear;

// Input signal
x = input("Enter the input sequence :");
N = length(x);

// Initialize DFT output
X = zeros(1, N);

// DFT calculation
for k = 1:N
    for n = 1:N
        X(k) = X(k) + x(n) * exp(-%i * 2 * %pi * (k-1) * (n-1) / N);
    end
end

// FFT calculation
X_fft = fft(x);

// Display results
disp("DFT of the sequence is:");
disp(X);

disp("FFT of the sequence is:");
disp(X_fft);

// Magnitude and Phase (DFT)
magX = abs(X);
phaseX = atan(imag(X), real(X));

// Magnitude and Phase (FFT)
magFFT = abs(X_fft);
phaseFFT = atan(imag(X_fft), real(X_fft));


// -------- DFT PLOTS --------
figure(1);

subplot(2,1,1);
plot2d3(0:N-1, magX);
title("DFT Magnitude Spectrum");
xlabel("k");
ylabel("|X(k)|");

subplot(2,1,2);
plot2d3(0:N-1, phaseX);
title("DFT Phase Spectrum");
xlabel("k");
ylabel("Phase (radians)");


// -------- FFT PLOTS --------
figure(2);

subplot(2,1,1);
plot2d3(0:N-1, magFFT);
title("FFT Magnitude Spectrum");
xlabel("k");
ylabel("|X(k)|");

subplot(2,1,2);
plot2d3(0:N-1, phaseFFT);
title("FFT Phase Spectrum");
xlabel("k");
ylabel("Phase (radians)");

```

## OUTPUT: 
<img width="1920" height="1200" alt="Screenshot 2026-03-10 140821" src="https://github.com/user-attachments/assets/29864140-572b-483c-ba4f-95d94efec3f8" />


## RESULT: 
 Thus the DFT and FFT of the given sequence is obtained and verified.
