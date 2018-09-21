Implementation for 4x upsampling of ADC input data. FIR coefficients computed using MATLAB

upfac = 7;
alpha = 0.5;
h1 = intfilt(upfac,2,0.1);
