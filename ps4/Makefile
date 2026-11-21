TITLE := MCHAWE CLOUD
VERSION := 1.00
TITLE_ID := MCHW00001
CONTENT_ID := IV0000-MCHW00001_00-MCHAWECLD000000
LIBS := -lc -lkernel
CFLAGS := --target=x86_64-pc-freebsd12-elf -fPIC -funwind-tables -c -isysroot $(OO_PS4_TOOLCHAIN) -isystem $(OO_PS4_TOOLCHAIN)/include
LDFLAGS := -m elf_x86_64 -pie --script $(OO_PS4_TOOLCHAIN)/link.x --eh-frame-hdr -L$(OO_PS4_TOOLCHAIN)/lib $(LIBS) $(OO_PS4_TOOLCHAIN)/lib/crt1.o
CC := clang
LD := ld.lld
INTDIR := build
OBJS := $(INTDIR)/main.o

all: eboot.bin

$(INTDIR):
	mkdir -p $(INTDIR)

$(INTDIR)/main.o: src/main.c | $(INTDIR)
	$(CC) $(CFLAGS) -o $@ $<

eboot.bin: $(OBJS)
	$(LD) $(INTDIR)/mchawe-cloud.elf -o $@ $(LDFLAGS) $(OBJS)
	$(OO_PS4_TOOLCHAIN)/bin/linux/create-fself -in=$(INTDIR)/mchawe-cloud.elf -out=$(INTDIR)/mchawe-cloud.oelf --eboot eboot.bin --paid 0x3800000000000011

clean:
	rm -rf $(INTDIR) eboot.bin pkg.gp4
