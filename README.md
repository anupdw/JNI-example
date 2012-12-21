This is a sample program to illustrate Java Native Interface

Type the following commands on terminal to generate the header files.
javac Hello.java
javah -jni Hello

Next, we create the dynamic library file for Hello.c

gcc -c -I/System/Library/Framework/JavaVM.fremwork/Headers Hello.c

gcc -dynamiclib -o libHelloImpl.jnilib Hello.o -framework JavaVM

This will create the dynamic shared library file libHelloImp.jnilib

The above commands are specific to Mac OS X Operating System. Linux/Windows will have different way to compile and generate dynamic shared object files.

Run the program using the command:
java Hello user1 3