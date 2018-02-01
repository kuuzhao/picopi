TARGET = testtts

CC = g++
LIBS = -lexpat -lsvoxpico
INC = -I../compat/include -I../lib
CFLAGS = $(INC) -fPIC -Wall -g -fpermissive
CXXFLAGS = $(INC) -fPIC -Wall -g -fpermissive

# CFLAGS = -fPIC -Wall -Wextra -O2 -g # C flags
# #LDFLAGS = -shared  # linking flags
# RM = rm -f  # rm command
# TARGET_LIB = testtts # target lib
 
# #SRCS = main.c src1.c src2.c # source files
SRCS := strdup16to8.c \
 		strdup8to16.c \
 		svox_ssml_parser.cpp \
 		com_svox_picottsengine.cpp \
 		main.cpp

OBJS := strdup16to8.o \
 		strdup8to16.o \
 		svox_ssml_parser.o \
 		com_svox_picottsengine.o \
 		main.o

$(TARGET): $(OBJS)
	$(CC) -Wl,-rpath=/home/liang/work/speech/pico/picopi/pico/lib -rdynamic -lm -L../lib/ ${OBJS} $(LIBS) -o $@
 
$(SRCS:.o):%.c
	$(CC) $(CFLAGS) -c $< -o $@

$(SRCS:.o):%.cpp
	$(CC) $(CXXFLAGS) -c $< -o $@

.PHONY: clean
clean:
	${RM} ${TARGET} ${OBJS}

