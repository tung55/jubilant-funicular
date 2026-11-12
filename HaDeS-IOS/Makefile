CC = gcc
CFLAGS = -m32 -c -ffreestanding -O2 -Wall -Wextra
AS = nasm
ASFLAGS = -f elf32
LD = ld
LDFLAGS = -m elf_i386

OBJS = boot.o kernel.o pmm.o string.o gui.o

all: myos.bin

boot.o: boot.asm
	$(AS) $(ASFLAGS) boot.asm -o boot.o

kernel.o: kernel.c
	$(CC) $(CFLAGS) kernel.c -o kernel.o

pmm.o: pmm.c
	$(CC) $(CFLAGS) pmm.c -o pmm.o

string.o: string.c
	$(CC) $(CFLAGS) string.c -o string.o

gui.o: gui.c
	$(CC) $(CFLAGS) gui.c -o gui.o

myos.bin: $(OBJS)
	$(LD) $(LDFLAGS) -T linker.ld -o myos.bin $(OBJS)

clean:
	rm -f *.o myos.bin
