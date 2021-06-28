#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=gunicorn3
PKG_VERSION:=20.1.0
PKG_RELEASE:=1

PKG_SOURCE:=gunicorn-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/g/gunicorn
PKG_HASH:=e0a968b5ba15f8a328fdfd7ab1fcb5af4470c28aaf7e55df02a99bc13138e6e8

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-gunicorn-$(PKG_VERSION)

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-gunicorn
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://gunicorn.org
  TITLE:=WSGI HTTP Server for UNIX (library)
  DEPENDS:=+python3
  VARIANT:=python3
endef

define Package/python3-gunicorn/description
    WSGI HTTP Server for UNIX (libraries)
endef

# Make sure that the binaries are not installed with the libraries
# That means adding some empty Py3Package/gunicorn3/install rules
define Py3Package/python3-gunicorn/install
	:
endef

define Package/gunicorn3
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=WSGI HTTP Server for UNIX
  URL:=https://gunicorn.org
  DEPENDS:=+python3 +python3-setuptools +python3-gunicorn
endef

define Package/gunicorn3/description
    WSGI HTTP Server for UNIX (daemon)
endef

define Package/gunicorn3/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/gunicorn \
		$(1)/usr/bin/gunicorn3
	$(LN) gunicorn3 $(1)/usr/bin/gunicorn
	# fix python exec path in scripts
	$(SED) 's/#!.*/#!\/usr\/bin\/python3/g' $(1)/usr/bin/gunicorn*
	#$(call Python3/FixShebang,$(1)/usr/bin/*)
endef

$(eval $(call Py3Package,python3-gunicorn))
$(eval $(call BuildPackage,python3-gunicorn))
$(eval $(call BuildPackage,python3-gunicorn-src))
$(eval $(call BuildPackage,gunicorn3))
