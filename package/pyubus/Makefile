#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=pyubus
PKG_VERSION:=0.1.1

PKG_SOURCE:=ubus-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/u/ubus
PKG_HASH:=7e57bda989bc35b48c7075d03ec2818226e722bbf1bde138d7e7ea26d462682a

PKG_BUILD_DIR:=$(BUILD_DIR)/pyubus-$(PKG_VERSION)
PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)


define Package/pyubus
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=pyubus
  URL:=https://gitlab.labs.nic.cz/turris/python-ubus
  DEPENDS:=+python3-light +libubus +libubox +libblobmsg-json
  VARIANT:=python3
endef

define Package/pyubus/description
Subset of libubus functions to be used directly from python
endef

$(eval $(call Py3Package,pyubus))
$(eval $(call BuildPackage,pyubus))
$(eval $(call BuildPackage,pyubus-src))

