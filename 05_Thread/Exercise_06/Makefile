.PHONY := clean all

CC := gcc
CUR_DIR := .
BIN_DIR := $(CUR_DIR)/bin
SRC_DIR := $(CUR_DIR)/src
EXE_FILE := $(CUR_DIR)/bin/sum_array

all:
	$(CC) -o $(EXE_FILE) $(SRC_DIR)/main.c -pthread

clean:
	rm -rf $(EXE_FILE)
