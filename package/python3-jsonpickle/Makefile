#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include ../../feeds/packages/lang/python/python3-package.mk

PKG_NAME:=python3-jsonpickle
PKG_VERSION:=2.0.0
PKG_RELEASE:=1

PKG_SOURCE:=jsonpickle-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/j/jsonpickle
PKG_HASH:=0be49cba80ea6f87a168aa8168d717d00c6ca07ba83df3cec32d3b30bfe6fb9a

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-jsonpickle-$(PKG_VERSION)

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-jsonpickle
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Python library for serializing any arbitrary object graph into JSON
  DEPENDS:=+python3-light
  VARIANT:=python3
endef

define Package/python3-jsonpickle/description
  Python library for serializing any arbitrary object graph into JSON
endef

$(eval $(call Py3Package,python3-jsonpickle))
$(eval $(call BuildPackage,python3-jsonpickle))
$(eval $(call BuildPackage,python3-jsonpickle-src))
