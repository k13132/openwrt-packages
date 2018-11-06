include $(TOPDIR)/rules.mk


PKG_NAME:=pigz
PKG_VERSION:=2.4
PKG_RELEASE:=1
PKG_MAINTAINER:=Zbynek Kocur <zbynek.kocur@fel.cvut.cz>
PKG_LICENSE:=zlib (http://zlib.net/zlib_license.html)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/madler/pigz.git
PKG_SOURCE_VERSION:=fe822cb435622c43f491013da77b127e9fe851a9
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)
PKG_BUILD_PARALLEL:=1


include $(INCLUDE_DIR)/package.mk


define Package/$(PKG_NAME)
   SUBMENU:=Compression
   SECTION:=utils
   CATEGORY:=Utilities
   TITLE:=A parallel implementation of gzip
   URL:=https://zlib.net/pigz/
   DEPENDS:=+zlib
endef


define Package/$(PKG_NAME)/description
Pigz, which stands for parallel implementation of gzip, is a fully functional replacement for gzip that exploits multiple processors and multiple cores to the hilt when compressing data. Pigz was written by Mark Adler, and uses the zlib and pthread libraries.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
endef


define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/pigz $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/unpigz $(1)/usr/bin
endef


$(eval $(call BuildPackage,$(PKG_NAME)))
