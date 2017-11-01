#
# Copyright (C) 2008-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pandas
PKG_VERSION:=0.21.0rc1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/84/97/ecd945c00c27e98c1540c788c2409de42e116e81fa9ca4c200fb2ec93c8f/
PKG_MD5SUM:=20b8d7142459e9ca73372a34aa792fc5
PKG_LICENSE:=BSD

PKG_BUILD_DEPENDS:=python3/host python3-setuptools/host python3-numpy/host python3-pytz/host python3-dateutil/host

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-$(PKG_NAME)
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python3-pandas
  URL:=http://pandas.pydata.org
  DEPENDS:=+python3 +python3-numpy +python3-dateutil +python3-pytz +python3-matplotlib
endef

define Package/python3-$(PKG_NAME)/description
  Powerful data structures for data analysis, time series, and statistics.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)/$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(STAGING_DIR)/$(PYTHON_PKG_DIR)
endef


$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
