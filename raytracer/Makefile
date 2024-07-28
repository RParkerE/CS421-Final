# Makefile for Haskell project

# Variables
STACK = stack
CABAL_FILE = haskell-raytracer.cabal
STACK_YAML = stack.yaml
APP_DIR = app
SRC_DIR = src
TEST_DIR = test

# Default target
.PHONY: all
all: build

# Build the project
.PHONY: build
build:
	$(STACK) build

# Run the main application
.PHONY: run
run:
	$(STACK) exec ray-tracer-exe

# Test the project
.PHONY: test
test:
	$(STACK) test

# Clean the project
.PHONY: clean
clean:
	$(STACK) clean

# Install dependencies
.PHONY: install
install:
	$(STACK) setup
	$(STACK) build --only-dependencies

# Generate Hoogle database
.PHONY: hoogle
hoogle:
	$(STACK) hoogle -- generate

# Format code using stylish-haskell
.PHONY: format
format:
	stylish-haskell -i $(APP_DIR)/*.hs $(SRC_DIR)/*.hs $(TEST_DIR)/*.hs

# Watch for changes and rebuild
.PHONY: watch
watch:
	$(STACK) build --file-watch

# Open the GHCi REPL
.PHONY: repl
repl:
	$(STACK) ghci
