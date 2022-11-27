CSFLAGS = -warn:4
DIR = ../csharp

default : log.out
       
log.out : test.exe
	mono $< > $@

test.exe : test.cs cholesky.dll
	mcs $(CSFLAGS) -reference:cholesky.dll -out:$@ $< 

cholesky.dll : $(DIR)/decomposed.cs
	mcs $(CSFLAGS) -target:library -out:$@ $^


.PHONEY : clean 

clean : 
	rm -f log.out test.exe
