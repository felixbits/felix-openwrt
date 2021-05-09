#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include ../../feeds/packages/lang/python/python3-package.mk

PKG_NAME:=python3-lazy-import
PKG_VERSION:=0.2.2
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-lazy-import-$(PKG_VERSION)

define Package/python3-lazy-import
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=A module for lazy loading of Python modules
  DEPENDS:=+python3-light +python3-six
  VARIANT:=python3
endef

define Package/python3-lazy-import/description
  A module for lazy loading of Python modules
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

$(eval $(call Py3Package,python3-lazy-import))
$(eval $(call BuildPackage,python3-lazy-import))
$(eval $(call BuildPackage,python3-lazy-import-src))
