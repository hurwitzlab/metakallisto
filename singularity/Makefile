SINGULARITY = /usr/local/bin/singularity
IMG = metakallisto-0.1.0.img
DEF = image.def
SIZE = 2048

run:
	sudo $(SINGULARITY) run $(IMG)

clean:
	rm -f $(IMG)

img: clean
	sudo $(SINGULARITY) build $(IMG) $(DEF)

img_old: clean
	sudo $(SINGULARITY) create --size $(SIZE) $(IMG)
	sudo $(SINGULARITY) bootstrap $(IMG) $(DEF)

shell:
	sudo $(SINGULARITY) shell --writable -B /data:/work -B $(HOME):/home1 -B $(shell pwd):/tmp $(IMG)
