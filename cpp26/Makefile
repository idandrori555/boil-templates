# Compilers
CC := clang++

# Common flags
FLAGS := -Wall -std=c++26

# Source files
SOURCES := $(wildcard *.cpp)

# Build directory
BUILD_DIR := build

# Output names
OUT_EXE_NAME := program
OUT_LINUX := $(BUILD_DIR)/$(OUT_EXE_NAME)

# Default target
all: linux run

# Ensure build directory exists
$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

# Build Linux version
linux: $(BUILD_DIR)
	$(CC) $(FLAGS) $(SOURCES) -o $(OUT_LINUX)
	@echo "✅ Compiled for Linux -> $(OUT_LINUX)"

run: $(OUT_LINUX)
	./$(OUT_LINUX)

# Clean up
clean:
	rm -rf $(BUILD_DIR)

.PHONY: linux clean all

