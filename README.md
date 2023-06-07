# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
/* write all the steps invloved */
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: REXON.J.P
RegisterNumber: 212222050048
```
### PROGRAM ENCODER
```
module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```




### RTL LOGIC  

![WhatsApp Image 2023-06-07 at 14 11 33](https://github.com/Rex0n15/Experiment-08-Encoders-and-decoders-/assets/130550796/10849967-58de-42f5-b4a7-73acefb027dd)







### TIMING DIGRAMS  

![WhatsApp Image 2023-06-07 at 14 11 33](https://github.com/Rex0n15/Experiment-08-Encoders-and-decoders-/assets/130550796/e578f242-653b-443e-a7a1-23488b36dfe5)




### TRUTH TABLE 
![WhatsApp Image 2023-06-07 at 14 35 51](https://github.com/Rex0n15/Experiment-08-Encoders-and-decoders-/assets/130550796/c81af9b9-7407-4b2b-a52e-fcd6a17ba665)







### PROGRAM DECODER
```
module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0=(~a&~b&~c);
assign d1=(~a&~b&c);
assign d2=(~a&b&~c);
assign d3=(~a&b&c);
assign d4=(a&~b&~c);
assign d5=(a&~b&c);
assign d6=(a&b&~c);
assign d7=(a&b&c);
endmodule

```




### RTL LOGIC 


![WhatsApp Image 2023-06-07 at 14 22 15](https://github.com/Rex0n15/Experiment-08-Encoders-and-decoders-/assets/130550796/e7c66e69-cae0-47df-9f61-61db728a5953)



### TIMING DIGRAMS  

![WhatsApp Image 2023-06-07 at 14 27 37](https://github.com/Rex0n15/Experiment-08-Encoders-and-decoders-/assets/130550796/505393d8-d8c2-4402-92c9-72f9fefb2dc8)


### TRUTH TABLE 

![WhatsApp Image 2023-06-07 at 14 35 59](https://github.com/Rex0n15/Experiment-08-Encoders-and-decoders-/assets/130550796/8e41483a-b29a-4238-aef8-795453021601)


### RESULT

encoders and decoders are verified
