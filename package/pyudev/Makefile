#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=pyudev
PKG_VERSION:=0.22.0
PKG_RELEASE:=1

PKG_SOURCE:=pyudev-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pyudev
PKG_HASH:=skip

PKG_MAINTAINER:=Kishan Go. <kishanpgondaliya@gmail.com>
PKG_LICENSE:=GNU 2.0
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/pyudev-$(PKG_VERSION)

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/pyudev
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=pyudev is a LGPL licensed, pure Python binding for libudev
  DEPENDS:=+python3-light
  VARIANT:=python3
endef

define Package/pyudev/description
  pyudev is a LGPL licensed, pure Python binding for libudev
endef

$(eval $(call Py3Package,pyudev))
$(eval $(call BuildPackage,pyudev))

