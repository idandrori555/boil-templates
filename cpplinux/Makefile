# Compilers
LCC := clang++

# Common flags
FLAGS := -Wall -static

# Source files
SOURCES := $(wildcard *.cpp)

# Build directory
BUILD_DIR := build

# Output names
OUT := program
OUT_LINUX := $(BUILD_DIR)/$(OUT)

# Default target
all: linux run

# Ensure build directory exists
$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

# Build Linux version
linux: $(BUILD_DIR)
	$(LCC) $(FLAGS) $(SOURCES) -o $(OUT_LINUX)
	@echo "✅ Compiled for Linux -> $(OUT_LINUX)"

run: $(OUT_LINUX)
	./$(OUT_LINUX)

# Clean up
clean:
	rm -rf $(BUILD_DIR)

.PHONY: windows linux clean all
