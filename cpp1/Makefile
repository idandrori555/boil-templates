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
OUT_LINUX := $(BUILD_DIR)/$(OUT)
OUT_WINDOWS := $(BUILD_DIR)/$(OUT)

# Default target
all: linux run

# Ensure build directory exists
$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

# Build Linux version
linux: $(BUILD_DIR)
	$(LCC) $(FLAGS) $(SOURCES) -o $(OUT_LINUX)
	@echo "✅ Compiled for Linux -> $(OUT_LINUX)"

# Build Windows version
windows: $(BUILD_DIR)
	$(WCC) $(FLAGS) $(SOURCES) -o $(OUT_WINDOWS)
	@echo "✅ Compiled for Windows -> $(OUT_WINDOWS)"

run: $(OUT_LINUX)
	./$(OUT_LINUX)

# Clean up
clean:
	rm -rf $(BUILD_DIR)

.PHONY: windows linux clean all
