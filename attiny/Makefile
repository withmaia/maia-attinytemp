all:
	avr-gcc -std=gnu99 -Os -mmcu=attiny85 -D F_CPU=8000000 -c main.c lib/dht.c lib/softuart.c
	avr-gcc -mmcu=attiny85 -o main.elf main.o dht.o softuart.o
	avr-objcopy -j .text -j .data -O ihex main.elf main.hex
	avrdude -P usb -p attiny85 -c usbtiny -e -U flash:w:main.hex

