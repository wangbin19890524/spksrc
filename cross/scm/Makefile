PKG_NAME = scm
PKG_VERS = 1.0.0
PKG_EXT = tar.gz
PKG_DIST_NAME = v$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/wangbin1989/SimpleCapabilityManager/archive/refs/tags
PKG_DIR = scm

DEPENDS =

BUILD_DEPENDS = native/go

LICENSE  = GPLv3

REQUIRED_MIN_DSM = 7

include ../../mk/spksrc.archs.mk

GO_SRC_DIR = $(EXTRACT_PATH)/SimpleCapabilityManager-$(PKG_VERS)
GO_BIN_DIR = $(GO_SRC_DIR)/bin

COMPILE_TARGET = scm_custom_compile
INSTALL_TARGET = scm_custom_install

include ../../mk/spksrc.cross-go.mk

.PHONY: scm_custom_compile
scm_custom_compile:
	@$(MSG) - Compile with go build
	cd $(GO_SRC_DIR) && env $(ENV) make build

.PHONY: scm_custom_install
scm_custom_install:
	@$(MSG) - Install scm binaries
	install -m 755 -d $(STAGING_INSTALL_PREFIX)/usr/local/bin
	install -m 755 $(GO_BIN_DIR)/* $(STAGING_INSTALL_PREFIX)/usr/local/bin
	install -m 755 $(GO_SRC_DIR)/src/first-install.sh $(STAGING_INSTALL_PREFIX)
