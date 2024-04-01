%%
clearvars;
clc
close all;
disp('Section-1 Complete')
%figure,plot(x)
%%
[x,Fs] = audioread("C:\Users\seema\Downloads\Gaussian-Noise-Removal-Using-LowpassFilter-main\Gaussian-Noise-Removal-Using-Lowpass-Filter-main\dsp+new.wav");
%sound(x,Fs);
N = size(x,1);% length of signal
f = Fs*(0:N-1)*N;% frequency range
T = 1/Fs;% sampling time
L = N; % length of signal
t = (0:L-1)*T; %time vector
disp('Section-2 Complete');
%%
noisy1 = awgn(x,30);
noisy2 = awgn(x,25);
noisy3 = awgn(x,75);
audiowrite('noisy1.wav',noisy1,Fs);
audiowrite('noisy2.wav',noisy2,Fs);
audiowrite('noisy3.wav',noisy3,Fs);
disp('Section-3 Complete');
%%
[audio,audio_freqs]=audioread("C:\Users\seema\Downloads\Gaussian-Noise-RemovalUsing-Lowpass-Filter-main\Gaussian-Noise-Removal-Using-Lowpass-Filtermain\dsp+new.wav");
Length=length(audio);
df=audio_freqs/Length;
freq_audio=0:df:audio_freqs/2-df;
disp('Section-4 Complete');
%%
%sound(noisy1, Fs);
xn1 = x + noisy1;
audiowrite('Noisy-Signal1.wav',xn1,Fs);
%sound(xn1, Fs);
[audio1,audio_freqs1]=audioread('noisy1.wav');
Length1=length(audio1);
df=audio_freqs1/Length1;
freq_audio1=0:df:audio_freqs1/2-df;
%sound(noisy2, Fs);
xn2 = x + noisy2;
audiowrite('Noisy-Signal2.wav',xn2,Fs);
%sound(xn2, Fs);
[audio2,audio_freqs2]=audioread('noisy2.wav');
Length2=length(audio2);
df=audio_freqs2/Length2;
freq_audio2=0:df:audio_freqs2/2-df;
%
xn3 = x + noisy3;
audiowrite('Noisy-Signal3.wav',xn3,Fs);
[audio3,audio_freqs3]=audioread('noisy3.wav');
Length3=length(audio3);
df=audio_freqs3/Length3;
freq_audio3=0:df:audio_freqs3/2-df;
%
figure,
stem(t , x);
title('Input Signal: Time-domain'); xlabel('time(seconds)');ylabel('Amplitude');
%
figure,
FFT_audio=(fft(audio))/length(fft(audio));
subplot(2,2,1);
plot(freq_audio,abs(FFT_audio(1:length(freq_audio))));
title('FFT of Input Audio');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
FFT_audio1=(fft(audio1))/length(fft(audio1));
subplot(2,2,3);
plot(freq_audio1,abs(FFT_audio1(1:length(freq_audio1))));
title('FFT of noisy signal 1(30 SNR)');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
FFT_audio2=(fft(audio2))/length(fft(audio2));
subplot(2,2,2);
plot(freq_audio2,abs(FFT_audio2(1:length(freq_audio2))));
title('FFT of noisy signal 2(25 SNR)');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
FFT_audio3=(fft(audio3))/length(fft(audio3));
subplot(2,2,4);
plot(freq_audio3,abs(FFT_audio3(1:length(freq_audio3))));
title('FFT of noisy signal 3(75 SNR)');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
disp('Section-5 Complete');
%%
load("C:\Users\seema\Downloads\Gaussian-Noise-Removal-Using-Lowpass-Filtermain\Gaussian-Noise-Removal-Using-Lowpass-Filter-main\workspace.mat");
filtered_signal1 = filter(Hd1,xn1);
filtered_signal2 = filter(Hd1,xn2);
filtered_signal3 = filter(Hd1,xn3);
filtered_signal4 = filter(Hd1,x);
disp('Section-6 Complete');
%%
audiowrite('Output1.wav',filtered_signal1,Fs);
audiowrite('Output2.wav',filtered_signal2,Fs);
audiowrite('Output3.wav',filtered_signal3,Fs);
audiowrite('Output.wav',filtered_signal4,Fs);
disp('Section-7 Complete');
%%
[audio1,audio_freqs1]=audioread('Output1.wav');
Length1=length(audio1);
df=audio_freqs1/Length1;
freq_audio1=0:df:audio_freqs1/2-df;
[audio2,audio_freqs2]=audioread('Output2.wav');
Length2=length(audio2);
df=audio_freqs2/Length2;
freq_audio2=0:df:audio_freqs2/2-df;
[audio3,audio_freqs3]=audioread('Output3.wav');
Length3=length(audio3);
df=audio_freqs3/Length3;
freq_audio3=0:df:audio_freqs3/2-df;
[audio,audio_freqs]=audioread('Output.wav');
Length=length(audio);
df=audio_freqs/Length;
freq_audio=0:df:audio_freqs/2-df;
figure,
FFT_audio=(fft(audio))/length(fft(audio));
subplot(2,2,1);
plot(freq_audio,abs(FFT_audio(1:length(freq_audio))));
title('Filtered Input Audio');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
FFT_audio1=(fft(audio1))/length(fft(audio1));
subplot(2,2,3);
plot(freq_audio1,abs(FFT_audio1(1:length(freq_audio1))));
title('Filtered Noisy Signal 1 (30 SNR)');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
FFT_audio2=(fft(audio2))/length(fft(audio2));
subplot(2,2,2);
plot(freq_audio2,abs(FFT_audio2(1:length(freq_audio2))));
title('Filtered Noisy Signal 2 (25 SNR)');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
FFT_audio3=(fft(audio3))/length(fft(audio3));
subplot(2,2,4);
plot(freq_audio3,abs(FFT_audio3(1:length(freq_audio3))));
title('Filtered Noisy Signal 3 (75 SNR)');
xlabel('Frequency(Hz)');
ylabel('Amplitude');
disp('Section-8 Complete');
