#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-ltun
PKG_SOURCE_DATE:=2023-05-07
PKG_SOURCE_VERSION:=62b3b0fd70ec61060318c8a1ae1608ba1209a30e
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vdudouyt/ltun
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=Zbynek Kocur <zbynek.kocur@fel.cvut.cz>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define Package/lua-ltun
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Lua TUN/TAP Library
  URL:=https://github.com/vdudouyt/ltun
  DEPENDS:=+liblua +kmod-tun
endef

define Package/lua-ltun/description
  ltun is a Lua module which let you create TUN/TAP device very easily.
endef

define Build/Configure
endef

define Package/lua-ltun/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(CP) $(PKG_BUILD_DIR)/ltun.so $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,lua-ltun))
