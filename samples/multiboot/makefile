CC       = gcc
CFLAGS   = -m32 -march=i386 -I. -Wall -Wextra -nostdlib -fno-builtin -nostartfiles -nodefaultlibs

LD       = ld
LDFLAGS  = -m elf_i386

OBJFILES = boot.o kernel.o

all: kernel.bin

.s.o:
	$(CC) $(CFLAGS) -o $@ -c $<
	
.c.o:
	$(CC) $(CFLAGS) -o $@ -c $<
 
kernel.bin: $(OBJFILES)
	$(LD) $(LDFLAGS) -T linker.ld -o $@ $^
 
clean:
	$(RM) $(OBJFILES) kernel.bin