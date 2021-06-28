#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=python3-pyserial
PKG_VERSION:=3.3

PKG_SOURCE:=pyserial-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pyserial
PKG_HASH:=2949cddffc2b05683065a3cd2345114b1a49b08df8cb843d69ba99dc3e19edc2

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-pyserial-$(PKG_VERSION)
PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)


define Package/python3-pyserial
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-pyserial
  URL:=https://github.com/pyserial/pyserial
  DEPENDS:=+python3-light
  VARIANT:=python3
endef

define Package/python3-pyserial/description
This module encapsulates the access for the serial port. It provides backends
for Python running on Windows, OSX, Linux, BSD (possibly any POSIX compliant
system) and IronPython. The module named "serial" automatically selects the
appropriate backend.
endef

$(eval $(call Py3Package,python3-pyserial))
$(eval $(call BuildPackage,python3-pyserial))
$(eval $(call BuildPackage,python3-pyserial-src))

