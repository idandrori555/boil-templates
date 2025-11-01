# Compilers
WCC := i686-w64-mingw32-g++
LCC := clang++

# Common flags
CFLAGS := -Wall -static

# Build directories
BUILD_DIR := build

# Object directories
OBJ_DIR_LINUX := $(BUILD_DIR)/obj/linux
OBJ_DIR_WINDOWS := $(BUILD_DIR)/obj/windows

# Source files
SOURCES := $(wildcard *.cpp)

# Output names
OUT := program
OUT_LINUX := $(BUILD_DIR)/$(OUT)-linux
OUT_WINDOWS := $(BUILD_DIR)/$(OUT)-windows

# Object files
OBJS_LINUX := $(patsubst %.cpp,$(OBJ_DIR_LINUX)/%.o,$(SOURCES))
OBJS_WINDOWS := $(patsubst %.cpp,$(OBJ_DIR_WINDOWS)/%.o,$(SOURCES))

# Default target
all: linux windows

# Ensure build directories exist
$(OBJ_DIR_LINUX):
	mkdir -p $(OBJ_DIR_LINUX)

$(OBJ_DIR_WINDOWS):
	mkdir -p $(OBJ_DIR_WINDOWS)

# Compile object files (Linux)
$(OBJ_DIR_LINUX)/%.o: %.cpp | $(OBJ_DIR_LINUX)
	$(LCC) $(CFLAGS) -c $< -o $@

# Compile object files (Windows)
$(OBJ_DIR_WINDOWS)/%.o: %.cpp | $(OBJ_DIR_WINDOWS)
	$(WCC) $(CFLAGS) -c $< -o $@

# Linux build
linux: $(OBJS_LINUX)
	$(LCC) $(CFLAGS) $(OBJS_LINUX) -o $(OUT_LINUX)
	@echo "✅ Compiled for Linux -> $(OUT_LINUX)"

# Windows build
windows: $(OBJS_WINDOWS)
	$(WCC) $(CFLAGS) $(OBJS_WINDOWS) -o $(OUT_WINDOWS)
	@echo "✅ Compiled for Windows -> $(OUT_WINDOWS)"

# Clean
clean:
	rm -rf $(BUILD_DIR)

.PHONY: all linux windows clean

