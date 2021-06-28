#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include ../../feeds/packages/lang/python/python3-package.mk

PKG_NAME:=python-gattlib
PKG_VERSION:=0.20201113
PKG_RELEASE:=1

PKG_MAINTAINER:=Kishan Go. <kishanpgondaliya@gmail.com>
PKG_LICENSE:=GNU 2.0
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-gattlib

define Package/python-gattlib
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Python Gattlib
  DEPENDS:=+python3 +bluez-libs +glib2 +libstdcpp +boost-python3 +boost-thread +boost
  VARIANT:=python3
endef

define Package/python-gattlib/description
  GattLib is a library used to access Generic Attribute Profile (GATT) protocol of BLE (Bluetooth Low Energy) devices.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

$(eval $(call Py3Package,python-gattlib))
$(eval $(call BuildPackage,python-gattlib))
