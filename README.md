Implementation for 4x upsampling of ADC input data. FIR coefficients computed using MATLAB

upfac = 4;
alpha = 0.5;
h1 = intfilt(upfac,6,0.1);

How it works:
1. From PS
 -The dac data is transmitted from the test.py
 -The DAC input is rerouted to the ADC
 -Only one of the two ADC is passed through a FIR filter. The filter is 
  operated at 250MHz and produces 16 bit signed output. With 4x upsampling,
  the FIR produces two 16-bit samples per cycle: 32 downto 16 and 15 down to 0.
  These data is than passed to the bram, based on the adc-dac-bram example, and 
  is read out using the server.
