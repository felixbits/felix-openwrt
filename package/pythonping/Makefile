#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=pythonping
PKG_VERSION:=1.1.0

PKG_SOURCE:=pythonping-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pythonping
PKG_HASH:=71199bdeee942ba1258b65f88ca5624278e63b31e7643ee8ca7292d2f5f77e99

PKG_BUILD_DIR:=$(BUILD_DIR)/pythonping-$(PKG_VERSION)
PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)


define Package/pythonping
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=pythonping
  URL:=https://github.com/alessandromaggio/pythonping
  DEPENDS:=+python3-light
  VARIANT:=python3
endef

define Package/pythonping/description

endef

$(eval $(call Py3Package,pythonping))
$(eval $(call BuildPackage,pythonping))

