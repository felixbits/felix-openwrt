#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include ../../feeds/packages/lang/python/python3-package.mk

PKG_NAME:=python-pybluez
PKG_VERSION:=0.23
PKG_RELEASE:=1

PKG_SOURCE:=PyBluez-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/P/PyBluez
PKG_HASH:=c8f04d2e78951eaa9de486b4d49381704e8943d0a6e6e58f55fcd7b8582e90de

PKG_MAINTAINER:=Kishan Go. <kishanpgondaliya@gmail.com>
PKG_LICENSE:=GNU 2.0
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/pybluez-$(PKG_VERSION)

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-pybluez
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Python wrapper for the BlueZ Bluetooth stack
  DEPENDS:=+python3-light +bluez-libs +python-gattlib
  VARIANT:=python3
endef

define Package/python-pybluez/description
  Bluetooth Python extension module
endef

$(eval $(call Py3Package,python-pybluez))
$(eval $(call BuildPackage,python-pybluez))
