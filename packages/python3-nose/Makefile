#
# Copyright (C) 2008-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=nose
PKG_VERSION:=1.3.7
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://pypi.python.org/packages/source/n/$(PKG_NAME)/
PKG_MD5SUM:=4d3ad0ff07b61373d2cefc89c5d0b20b

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python-host.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk


define Package/python3-$(PKG_NAME)
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python3-nose
  URL:=http://readthedocs.org/docs/nose/
  DEPENDS:=+python3
endef

define Package/python3-$(PKG_NAME)/description
  Nose extends the test loading and running features of unittest, making it easier to write, find and run tests.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Host/Compile
	$(call Build/Compile/HostPy3Mod,,install --prefix="" --root="$(STAGING_DIR_HOSTPKG)")
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)/$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(STAGING_DIR)/$(PYTHON_PKG_DIR)
endef

define Host/Install
endef

$(eval $(call HostBuild))

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
