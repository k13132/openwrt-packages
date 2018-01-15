#
# Copyright (C) 2008-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=dateutil
PKG_VERSION:=2.6.1
PKG_RELEASE:=1
PKG_LICENSE:=BSD-2-Clause

PKG_SOURCE:=python-$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/54/bb/f1db86504f7a49e1d9b9301531181b00a1c7325dc85a29160ee3eaa73a54/
PKG_MD5SUM:=db38f6b4511cefd76014745bb0cc45a4

PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)
HOST_UNPACK=$(HOST_TAR) -C $(HOST_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python-host.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk


define Package/python3-$(PKG_NAME)
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python3-dateutil
  URL:=https://dateutil.readthedocs.org
  DEPENDS:=+python3 +python3-six
endef

define Package/python3-$(PKG_NAME)/description
  The dateutil module provides powerful extensions to the datetime module available in the Python standard library.
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
