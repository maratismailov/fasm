# CC = fasm
# LIBS = asmlib/fmt.o asmlib/str.o asmlib/sys.o asmlib/mth.o
# .PHONY: default compile build once dump hex run
# compile: asmlib.fmt.asm asmlib.str.asm asmlib.sys.asm asmlib.mth.asm
# 	fasm asmlib.fmt.asm && fasm asmlib/str.asm && fasm asmlib/sys.asm && fasm asmlib/mth.asm
# build: main.asm
# 	$(CC) main.asm
# 	ld main.o $(LIBS) -o main
# once: main.asm
# 	$(CC) main.asm
# 	ld main.o -o main
# dump: main
# 	objdump -S -M intel -d main > obj.dump
# 	cat obj.dump
# hex: main
# 	hexeditor main
# run: main
# 	./main


FILE_IN = $(wildcard *.asm)
OBJ_FILE := $(patsubst %asm,%o,$(FILE_IN))
FILE_OUT := $(patsubst %.asm,%,$(FILE_IN))
CC = fasm
LIBS = asmlib/fmt.o asmlib/str.o asmlib/sys.o asmlib/mth.o
.PHONY: default compile build once dump hex run
default: $(FILE_IN)
	$(CC) $(FILE_IN)
	ld $(OBJ_FILE) -o $(FILE_OUT)
	./$(FILE_OUT)
build: $(FILE_IN)
	$(CC) $(FILE_IN)
	ld $(OBJ_FILE) $(LIBS) -o $(FILE_OUT)
once: $(FILE_IN)
	$(CC) $(FILE_IN)
	ld $(OBJ_FILE) -o $(FILE_OUT)
run: $(FILE_OUT)
	./$(FILE_OUT)
hex: $(FILE_OUT)
	hexeditor $(FILE_OUT)
dump: $(FILE_OUT)
	objdump -S -M intel -d $(FILE_OUT) > obj.dump'
