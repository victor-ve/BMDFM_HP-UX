# Makefile

#==============================================================================
# IA-64 HP-UX, GNU C
#------------------------------------------------------------------------------
CC = gcc -milp32
OPTIONS = -O3 -fPIC
#==============================================================================

MATH = -lm
PSM = -lrt

all: cflp_udf.o fastlisp BMDFMldr BMDFMsrv CPUPROC

cflp_udf.o: cflp_udf.c cflp_udf.h
	$(CC) $(OPTIONS) -c cflp_udf.c

fastlisp: fastlisp.o cflp_udf.o
	$(CC) -o fastlisp fastlisp.o cflp_udf.o $(MATH) $(PSM)

BMDFMldr: BMDFMldr.o cflp_udf.o
	$(CC) -o BMDFMldr BMDFMldr.o cflp_udf.o $(MATH) $(PSM)

BMDFMsrv: BMDFMsrv.o cflp_udf.o
	$(CC) -o BMDFMsrv BMDFMsrv.o cflp_udf.o $(MATH) $(PSM)

CPUPROC: CPUPROC.o cflp_udf.o
	$(CC) -o CPUPROC CPUPROC.o cflp_udf.o $(MATH) $(PSM)

clean:
	rm -f cflp_udf.o fastlisp BMDFMldr BMDFMsrv CPUPROC 2>/dev/null

