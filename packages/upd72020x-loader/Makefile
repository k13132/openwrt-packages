####################################################
# Project: 
#
# Type:   OpenWRT Makefile
# Author: Zbynek Kocur (zbynek.kocur@fel.cvut.cz)
#
# Copyright (C) 2020 CTU in Prague
####################################################

include $(TOPDIR)/rules.mk

PKG_NAME:=upd72020x-loader
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/markusj/upd72020x-load.git
PKG_SOURCE_VERSION:=d87965f9c6b795908d9ddccb686bb7303e6bc0f3
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
   SECTION:=utils
   CATEGORY:=Utilities
   TITLE:=upd72020x-loader
   URL:=https://github.com/markusj/upd72020x-load
endef

define Package/$(PKG_NAME)/description
upd72020x-load is a Linux userspace firmware loader for Renesas uPD720201/uPD720202 familiy USB 3.0 controllers.
It provides the functionality to upload the firmware required for certain extension cards before they can used with Linux.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/lib/firmware
	$(CP) ./firmware/K2013080.mem $(1)/lib/firmware

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/upd72020x-loader.init $(1)/etc/init.d/upd72020x-loader

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/upd72020x-load $(1)/usr/sbin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
