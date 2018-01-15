#
# Copyright (C) 2008-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cycler
PKG_VERSION:=0.10.0
PKG_RELEASE:=1

PKG_SOURCE_URL:=https://github.com/matplotlib/cycler
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=e45ae7d50b8f2e0d131eca72028bed7a58773e47
PKG_LICENSE:=BSD

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz

PKG_BUILD_DEPENDS:=python3

HOST_PYTHON3_PACKAGE_BUILD_DEPENDS:="six"

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python-host.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk


define Package/python3-$(PKG_NAME)
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python3-cycler
  URL:=http://matplotlib.org/cycler/
  DEPENDS:=+python3 +python3-six
endef

define Package/python3-$(PKG_NAME)/description
  Composable style cycles.
endef

define Host/Compile
	$(call Build/Compile/HostPy3Mod,,install --prefix="" --root="$(STAGING_DIR_HOSTPKG)")
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python3-$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

define Host/Install
endef

$(eval $(call HostBuild))

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
