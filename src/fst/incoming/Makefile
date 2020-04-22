# ********************************************************************** #
# This is a makefile that builds the XFST Bulgarian morphological parser #
# ********************************************************************** #

# The parser was written by Ventsislav Zhechev.
# http://www.sfs.uni-tuebingen.de/iscl/Theses/zhechev.pdf


# Tools used when compiling the transducers

ifeq (victorio.uit.no, $(shell hostname))
XFST = /opt/sami/xerox/c-fsm/ix86-linux2.6-gcc3.4/bin/fst -utf8
LEXC = /opt/sami/xerox/bin/lexc -utf8
endif

XFST = fst -utf8
#XFST = xfst -utf8
LEXC = lexc -utf8


# Here we build the parser

bul.fst: ../bin/bul.fst
../bin/bul.fst: b
	@echo
	@echo "*** Building phon-kal.fst ***" ;
	@echo
	@printf "source $< \n\
	save stack $@ \n\
	quit \n" > ../tmp/phon-script
	$(XFST) < ../tmp/phon-script
	@rm -f ../tmp/phon-script




clean:
	@rm -f ../bin/*.bin ../bin/*.fst ../bin/*.save


