#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include ../../feeds/packages/lang/python/python3-package.mk

PKG_NAME:=python3-requests
PKG_VERSION:=2.23.0
PKG_RELEASE:=1

PKG_SOURCE:=requests-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/r/requests
PKG_HASH:=b3f43d496c6daba4493e7c431722aeb7dbc6288f52a6e04e7b6023b0247817e6

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-requests-$(PKG_VERSION)

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-requests
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=HTTP library for Python
  URL:=https://2.python-requests.org/
  DEPENDS:=+python3-light +python3-chardet +python3-idna +python3-urllib3 +python3-certifi
  VARIANT:=python3
endef

define Package/python3-requests/description
  Requests is the only Non-GMO HTTP library for Python, safe for human consumption
endef

$(eval $(call Py3Package,python3-requests))
$(eval $(call BuildPackage,python3-requests))
$(eval $(call BuildPackage,python3-requests-src))
