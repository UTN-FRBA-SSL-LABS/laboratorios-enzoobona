# Nombre del ejecutable final
PROGRAMA := calc3
BISON := parser3 # Por si cambian los nombres de los archivos
FLEX := scanner3

# Compilador
CC := gcc

# Regla principal
all: $(PROGRAMA)

# Regla para construir la calculadora a partir del parser y el scanner
# Bison genera: parser3.tab.c y parser3.tab.h
# Flex genera:  lex.yy.c
$(PROGRAMA): parser3.y scanner3.l
	bison -d $(BISON).y
	flex $(FLEX).l
	$(CC) $(BISON).tab.c lex.yy.c -o $(PROGRAMA)
# Regla para limpiar todos los archivos generados
clean:
	rm -f $(PROGRAMA) lex.yy.c $(BISON).tab.c $(BISON).tab.h
.PHONY: all clean
