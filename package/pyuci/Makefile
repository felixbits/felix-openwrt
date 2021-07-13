#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=pyuci
PKG_VERSION:=0.8.1

PKG_SOURCE:=pyuci-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pyuci
PKG_HASH:=9287fe41b427dc5c167592d429be48c1e6cfe276225681b1bdefddfe90d7e941

PKG_BUILD_DIR:=$(BUILD_DIR)/pyuci-$(PKG_VERSION)
PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)


define Package/pyuci
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=pyuci
  URL:=https://gitlab.nic.cz/turris/pyuci
  DEPENDS:=+python3-light +libuci
  VARIANT:=python3
endef

define Package/pyuci/description
Bindings for OpenWRT configuration interface called UCI and specifically library libuci.
You can use this library to access and set configuration from and to UCI.
endef

$(eval $(call Py3Package,pyuci))
$(eval $(call BuildPackage,pyuci))
$(eval $(call BuildPackage,pyuci-src))

