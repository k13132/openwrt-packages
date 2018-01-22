####################################################
# OpenWrt Makefile for FlowPing application
#
# File:   Makefile
# Author: Zbynek Kocur (zbynek.kocur@fel.cvut.cz)
#
#
####################################################


include $(TOPDIR)/rules.mk


PKG_NAME:=flowping
PKG_VERSION:=1.5.1
PKG_RELEASE:=1
PKG_MAINTAINER:=Ondrej Vondrous <ondrej.vondrous@fel.cvut.cz>
PKG_LICENSE:=GPL-3

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/k13132/flowping.git
PKG_SOURCE_VERSION:=cd2dc387b7d81c1b817dead8f53c83a673e69579
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)
PKG_BUILD_PARALLEL:=1


include $(INCLUDE_DIR)/package.mk


define Package/flowping
   SECTION:=k13132
   CATEGORY:=K13132
   TITLE:=FlowPing application (flowping)
   URL:=http://flowping.fel.cvut.cz
   DEPENDS:=+libpthread +libstdcpp +libc +librt
endef


define Package/flowping/description
	FlowPing application.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	$(CP) $(PKG_BUILD_DIR)/src/* $(PKG_BUILD_DIR)/
endef


define Package/flowping/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/flowping $(1)/usr/bin
endef


$(eval $(call BuildPackage,flowping))
