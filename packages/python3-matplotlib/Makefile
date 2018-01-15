include $(TOPDIR)/rules.mk

PKG_NAME:=matplotlib
PKG_RELEASE:=1
PKG_MAINTAINER:=Matplotlib Development Team <matplotlib-devel@python.org>
PKG_LICENSE:=BSD


#1.4.3
PKG_VERSION:=1.4.3
PKG_SOURCE_URL:=https://pypi.python.org/packages/bb/ac/485df0ecb15aa6fec1991945dc0cabfeb724a64f6729e34bab3c6a766813/
PKG_MD5SUM:=86af2e3e3c61849ac7576a6f5ca44267

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz

PKG_BUILD_DEPENDS:=python3

HOST_PYTHON3_PACKAGE_BUILD_DEPENDS:="six numpy dateutil libpng libfreetype six pytz pzparsing cycler"


include $(INCLUDE_DIR)/package.mk

include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-$(PKG_NAME)
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python3-matplotlib
  URL:=https://github.com/matplotlib/matplotlib
  DEPENDS:=+python3 +python3-setuptools +python3-six +python3-numpy +python3-dateutil +libpng +libfreetype +python3-pytz +python3-pyparsing +libc +libstdcpp +python3-cycler
endef

define Package/python3-$(PKG_NAME)/description
  Matplotlib is a Python 2D plotting library which produces publication quality figures in a variety of hardcopy formats and interactive environments across platforms.
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


$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
