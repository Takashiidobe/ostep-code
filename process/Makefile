DEBUG_FLAGS = -g -O0
RELEASE_FLAGS = -O3
BUILD_DIR = build
SRC_DIR = src
LIB_DIR = lib

SRCS = $(shell find $(SRC_DIR)/ -type f -name "*.c")
LIBS = $(shell find $(LIB_DIR)/ -type f -name "*.c")
PROGS = $(patsubst $(SRC_DIR)/%.c,$(BUILD_DIR)/%,$(SRCS))

all: $(PROGS)

build/%: $(SRC_DIR)/%.c $(LIBS) build_dir lib_dir
	$(CC) $(RELEASE_FLAGS) $(LIBS) $< -o $@

clean:
	rm -r $(BUILD_DIR)

build_dir:
	mkdir -p $(BUILD_DIR)

lib_dir:
	mkdir -p $(LIB_DIR)
