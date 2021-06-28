#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=bluezero
PKG_VERSION:=0.6.0
PKG_RELEASE:=1

#PKG_SOURCE:=bluezero-$(PKG_VERSION).tar.gz
#PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/b/bluezero
#PKG_HASH:=d94f0672b1de3ff0040801538143fe9a42c501d8db79bcd183c9e051b8da83bc

PKG_BUILD_DIR:=$(BUILD_DIR)/bluezero-$(PKG_VERSION)

#PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/bluezero
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Python wrapper for ble
  DEPENDS:=+python3-light +dbus-python
  VARIANT:=python3
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/bluezero/description
  Bluetooth Python extension module
endef

$(eval $(call Py3Package,bluezero))
$(eval $(call BuildPackage,bluezero))
