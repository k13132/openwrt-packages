include $(TOPDIR)/rules.mk

PKG_NAME:=matplotlib
PKG_RELEASE:=1
PKG_MAINTAINER:=Matplotlib Development Team <matplotlib-devel@python.org>
PKG_LICENSE:=BSD


#1.4.3
PKG_VERSION:=1.4.3
PKG_SOURCE_URL:=https://pypi.python.org/packages/6c/90/cf10bb2020d2811da811a49601f6eafcda022c6ccd296fd05aba093dee96/
PKG_MD5SUM:=64a8c5f85fe60caa7b536977254963d8

#Master
#PKG_VERSION:=2.1.x
#PKG_SOURCE_URL:=https://github.com/matplotlib/matplotlib.git
#PKG_SOURCE_PROTO:=git
#PKG_SOURCE_VERSION:=d78fb0ec4924c5574335e3745f8a20fee200188c


PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz

PKG_BUILD_DEPENDS:=python3/host python3-dev/host python3-setuptools/host python3-numpy/host python3-dateutil/host libpng/host libfreetype python3-six/host python3-pytz/host libc libstdcpp python3-pyparsing/host python3-cycler/host

include $(INCLUDE_DIR)/package.mk

$(call include_mk, python3-package.mk)

define Package/python3-$(PKG_NAME)
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python3-matplotlib
  URL:=https://github.com/matplotlib/matplotlib
  DEPENDS:=+python3 +python3-dev +python3-setuptools +python3-six +python3-numpy +python3-dateutil +libpng +libfreetype +python3-pytz +python3-pyparsing +libc +libstdcpp +python3-cycler
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
