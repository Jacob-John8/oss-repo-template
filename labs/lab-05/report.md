# Lab 04 Report - Build Systems

## Step 1 and 2

<img width="290" alt="BSs1" src="https://user-images.githubusercontent.com/75342856/153725163-2bf8878b-9263-415c-8994-e20a72b0a3ee.PNG">
<img width="282" alt="BSs2nmy" src="https://user-images.githubusercontent.com/75342856/153725167-8842dd96-dff3-4332-84ad-03d5f5157415.PNG">

## Step 3

![image](https://user-images.githubusercontent.com/75342856/153725385-06b759a6-839e-4b74-bcbe-a6764f466eff.png)

## Step 4

The output is its own file, see Step4_output.txt

## Step 5

![image](https://user-images.githubusercontent.com/75342856/153725643-0e411cba-0dae-42bf-bb14-9c690d3a4be1.png)

## PART 2
My Makefile
///
all: stat shar
clean:
	rm program.o source/statlib.a source/sharlib.so source/block.o static_block dynamic_block
main:
	gcc -c program.c -o program.o
stat: statlib main
	gcc program.o source/statlib.a -o static_block
shar: sharlib main
	gcc program.o source/sharlib.so -o dynamic_block -Wl,-rpath .
statlib: block 
	ar qc source/statlib.a source/block.o
sharlib: block
	gcc -shared -o source/sharlib.so source/block.o 
block:
	gcc -c source/block.c -o source/block.o
///
