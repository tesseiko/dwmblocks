
ifndef SUDO_USER

$(info running as user)

INSTALL_DIR ?= $(HOME)/.local/bin/statusbar
_USER?=$(USER)

else
$(info running as root)
INSTALL_DIR ?= /home/$(SUDO_USER)/.local/bin/statusbar
_USER?=$(SUDO_USER)
endif

TOOLNAMES := $(shell ls ./bin)
INSTALL_BINS ?= $(foreach tool, $(TOOLNAMES), $(INSTALL_DIR)/$(tool))

VPATH = bin
.PHONY: clean install all

all: tools

tools: $(INSTALL_BINS)

$(INSTALL_DIR)%: bin% | $(INSTALL_DIR)
	cp $^ $@
	chown -R $(_USER):$(_USER) $@


$(INSTALL_DIR):
	mkdir -p $@

clean:
	rm -rf $(INSTALL_DIR)

