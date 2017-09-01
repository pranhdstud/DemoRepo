all:main

main:main.o dynamicNum.o staticAlpha.o libStaticAlpha.a libDynamicNum.so
	gcc -o main main.o -L. -lStaticAlpha -lDynamicNum -lpthread
main.o:main.c
	gcc -I . -c main.c

staticAlpha.o:staticAlpha.h
		gcc -c staticAlpha.c
dynamicNum.o:dynamicNum.h
		gcc -Wall -fPIC -c dynamicNum.c 

libStaticAlpha.a:staticAlpha.o
		ar rcs libStaticAlpha.a staticAlpha.o
libDynamicNum.so:dynamicNum.c
		gcc -shared -o libDynamicNum.so dynamicNum.o
clean:
	rm main *.o *.a *.so
		
