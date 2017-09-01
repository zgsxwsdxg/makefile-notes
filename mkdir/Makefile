my_dirs = obj backup results
all: $(my_dirs)

obj :
	mkdir -p obj

backup:
	mkdir -p backup

results:
	mkdir -p results

.PHONY: clean

clean :
	@rmdir $(my_dirs)
