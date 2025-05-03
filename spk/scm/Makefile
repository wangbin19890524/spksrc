SPK_NAME = scm
SPK_VERS = 1.0.0
SPK_REV = 1
# SPK_ICON = src/scm.png

DEPENDS = cross/scm

MAINTAINER = wangbin1989
MAINTAINER_URL = https://github.com/wangbin1989

DISPLAY_NAME = scm
CHANGELOG = "Initial package release."
STARTABLE = no

LICENSE  = GPLv3

REQUIRED_MIN_DSM = 7.0

SPK_DEPENDS =

SERVICE_USER = auto
SERVICE_SETUP = src/service-setup.sh

# CONF_DIR = src/conf/
# DSM_UI_DIR = app
# DSM_UI_CONFIG = src/app/config

PRE_SERVICE_TARGET = scm_custom_pre_service_target

include ../../mk/spksrc.spk.mk

.PHONY: scm_custom_pre_service_target
scm_custom_pre_service_target:
	@$(MSG) "run scm_custom_pre_service_target"
	install -m 755 -d $$(dirname $(CURDIR)/$(SERVICE_SETUP))
	cp $(WORK_DIR)/SimpleCapabilityManager-$(SPK_VERS)/src/service-setup.sh $(CURDIR)/$(SERVICE_SETUP)
