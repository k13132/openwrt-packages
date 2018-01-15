#
# Copyright (C) 2008-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pandas
PKG_VERSION:=0.21.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/84/4c/622301f99725c6da76ae8079cb6b9091d9098098bd6b4eac47fb502b32f4/
PKG_MD5SUM:=6f14884caaa87a0824b5e93fe032b904
PKG_LICENSE:=BSD


include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

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
