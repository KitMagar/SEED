FLAGS    = -z execstack -fno-stack-protector
FLAGS_32 = -static -m32
TARGET   = server stack-L1 stack-L2 stack-L3 stack-L4
 
L1 = 239
L2 = 150
L3 = 200
L4 = 80

all: $(TARGET)

server: server.c
	gcc -o server server.c

stack-L1: stack.c
	gcc -DBUF_SIZE=$(L1) -DSHOW_FP $(FLAGS) $(FLAGS_32) -o $@ stack.c

stack-L2: stack.c
	gcc -DBUF_SIZE=$(L2) $(FLAGS) $(FLAGS_32) -o $@ stack.c

stack-L3: stack.c
	gcc -DBUF_SIZE=$(L3) -DSHOW_FP $(FLAGS) -o $@ stack.c

stack-L4: stack.c
	gcc -DBUF_SIZE=$(L4) -DSHOW_FP $(FLAGS) -o $@ stack.c

clean:
	rm -f badfile $(TARGET)

install:
	cp server ../bof-containers
	cp stack-* ../bof-containers

