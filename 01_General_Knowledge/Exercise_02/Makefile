
CUR_DIR := .
BIN_DIR := $(CUR_DIR)/bin
INC_DIR := $(CUR_DIR)/inc
OBJ_DIR := $(CUR_DIR)/obj
SRC_DIR := $(CUR_DIR)/src
LIB_DIR := $(CUR_DIR)/lib

C_FLAGS = -I $(INC_DIR)

create_objs:
	gcc -c -fPIC $(SRC_DIR)/add.c      -o $(OBJ_DIR)/add.o      $(C_FLAGS)
	gcc -c -fPIC $(SRC_DIR)/subtract.c -o $(OBJ_DIR)/subtract.o $(C_FLAGS)
	gcc -c -fPIC $(SRC_DIR)/multiply.c -o $(OBJ_DIR)/multiply.o $(C_FLAGS)
	gcc -c -fPIC $(SRC_DIR)/divide.c   -o $(OBJ_DIR)/divide.o   $(C_FLAGS)
	gcc -c       $(SRC_DIR)/main.c     -o $(OBJ_DIR)/main.o     $(C_FLAGS)

create_lib:
	gcc -shared $(OBJ_DIR)/add.o $(OBJ_DIR)/subtract.o $(OBJ_DIR)/multiply.o $(OBJ_DIR)/divide.o -o $(LIB_DIR)/libmath.so

all: create_objs create_lib
	gcc  $(OBJ_DIR)/main.o -L$(LIB_DIR) -lmath -o $(BIN_DIR)/use-shared-library
	# export LD_LIBRARY_PATH=$(pwd)/lib

clean:
	rm -rf $(OBJ_DIR)/*.o
	rm -rf $(LIB_DIR)/*.so
	rm -rf $(BIN_DIR)/use-shared-library
