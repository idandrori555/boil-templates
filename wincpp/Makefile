# Compilers
WCC := i686-w64-mingw32-g++
LCC := clang++

# Common flags
FLAGS := -Wall -static -std=c++23

# Source files
SOURCES := $(wildcard *.cpp)

# Build directory
BUILD_DIR := build

# Output names
OUT := program
OUT_WINDOWS := $(BUILD_DIR)/$(OUT)

# Default target
all: windows run

# Ensure build directory exists
$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

# Build Windows version
windows: $(BUILD_DIR)
	$(WCC) $(FLAGS) $(SOURCES) -o $(OUT_WINDOWS)
	@echo "✅ Compiled for Windows -> $(OUT_WINDOWS)"

run: windows
	./$(OUT_WINDOWS).exe

# Clean up
clean:
	rm -rf $(BUILD_DIR)

.PHONY: windows run all
