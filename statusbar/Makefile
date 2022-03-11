
STATUSBAR_TOOLS := $(wildcard ./bin/*)
TARGET_DIR ?= $(CURDIR)/bin
LINK_NAME ?= /home/$(SUDO_USER)/.local/bin/statusbar
install := $(LINK_NAME)


.PHONY: clean install all

all: .installed

.installed: $(STATUSBAR_TOOLS)
	touch .installed
	ln -sf $(TARGET_DIR) $(LINK_NAME)

clean:
	rm .installed
	rm $(LINK_NAME)
