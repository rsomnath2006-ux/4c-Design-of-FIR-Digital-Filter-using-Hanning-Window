# FIR-FILTER-DESIGN
# EXP 4 b: Design-of-FIR-Digital-Filter-using-Hanning-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are')  
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Hanning Window'); 
```
# CALCULATION:
![Han manu 1](https://github.com/user-attachments/assets/f6ff9b0c-d62f-4788-9261-1ea098d98999)
![Han manu 2](https://github.com/user-attachments/assets/9e20c484-f7f9-4349-9b33-c050d5349002)

# OUTPUT:
<img width="511" height="438" alt="LPF-Hanning Calculation" src="https://github.com/user-attachments/assets/2eb8fb13-6210-4983-8b02-57bc79c87d31" />
<img width="762" height="719" alt="LPF-Hanning graph" src="https://github.com/user-attachments/assets/ba720d95-ec85-4e21-bf42-596ba31adb1c" />

# RESULT: 

Thus design of low pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
``` 
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = 1-Wc/ %pi ; 
else 
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR HPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Hanning Window'); 
```
# CALCULATION:
![Hanning](https://github.com/user-attachments/assets/907d046f-378a-4997-b009-0c94cf0db682)

# OUTPUT:
<img width="495" height="485" alt="HPF-Hanning Calculation" src="https://github.com/user-attachments/assets/e4058b0d-3661-4fa6-b45b-1fc29cb36dc6" />
<img width="758" height="730" alt="HPF-Hanning graph" src="https://github.com/user-attachments/assets/3cd98d7a-e68d-4cbf-816c-1bfab7e60a61" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hanning Window'); 
```
# CALCULATION:
![Hanning](https://github.com/user-attachments/assets/b9c2be4c-d4c8-457e-a8fd-9ac846dbb369)

# OUTPUT:
<img width="591" height="463" alt="BPF-Hanning Calculation" src="https://github.com/user-attachments/assets/d0ae9e59-5a26-40ab-9fc3-644000f76f64" />
<img width="757" height="726" alt="BPF-Hanning Graph" src="https://github.com/user-attachments/assets/720a5de1-9863-41bf-8523-2a29442ddb67" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi); 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hanning Window');
```
# CALCULATION:
![Hanning](https://github.com/user-attachments/assets/0939196b-c07c-47da-a0a9-398c097bd168)

# OUTPUT:
<img width="570" height="505" alt="BSF-Hanning Calculation" src="https://github.com/user-attachments/assets/7d6e768f-c59c-4dfb-9cca-602aeaf4ba03" />
<img width="765" height="728" alt="BSF-Hanning Graph" src="https://github.com/user-attachments/assets/120e1312-71e5-4bfc-b5da-84ba1f594c12" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
