#
# Copyright (C) 2017 CTU in Prague
#
# Project: FlowTester
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-bwc
PKG_VERSION:=20190401
PKG_RELEASE:=1

PKG_MAINTAINER:=Zbynek Kocur <zbynek.kocur@fel.cvut.cz>
PKG_LICENSE:=Apache License, Version 2.0

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=luci
	CATEGORY:=LuCI
	SUBMENU:=2. Modules
	TITLE:=luci-bwc
	URL:=http://luci.subsignal.org/~jow/luci-bwc.c
	DEPENDS:=+libiwinfo +libiwinfo-lua
endef

define Package/$(PKG_NAME)/description
	Very simple bandwidth collector cache for LuCI realtime graphs. The package is extracted from the package luci-mod-status.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/bin
endef


$(eval $(call BuildPackage,$(PKG_NAME)))


