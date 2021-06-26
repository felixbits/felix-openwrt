#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=dbus-python
PKG_VERSION:=1.2.16
PKG_RELEASE:=1
PKG_MAINTAINER:=Kishan Go. <kishanpgondaliya@gmail.com>
PKG_LICENSE:=GNU 2.0

PKG_SOURCE:=dbus-python-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://dbus.freedesktop.org/releases/dbus-python
PKG_HASH:=11238f1d86c995d8aed2e22f04a1e3779f0d70e587caffeab4857f3c662ed5a4

PKG_BUILD_DIR:=$(BUILD_DIR)/dbus-python-$(PKG_VERSION)

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

define Package/dbus-python
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Python dbus library
  URL:=https://dbus.freedesktop.org/
  DEPENDS:=+python3 +libdbus +dbus-glib
endef

define Package/dbus-python/description
  Python module for interfacing with dbus
endef

CONFIGURE_ARGS += \
    PYTHON_VERSION=$(PYTHON3_VERSION) \
    PYTHON_LIBS="-L$(STAGING_DIR)/usr/lib -lpython$(PYTHON3_VERSION)" \
    PYTHON_INCLUDES=-I$(STAGING_DIR)/usr/include/python$(PYTHON3_VERSION)

TARGET_CFLAGS += \
    -I$(PKG_BUILD_DIR) \
    -I$(PKG_BUILD_DIR)/include \
    -I$(STAGING_DIR)/usr/include/dbus-1.0 \
    -I$(STAGING_DIR)/usr/lib/dbus-1.0/include \
    -I$(STAGING_DIR)/usr/include/glib-2.0

$(eval $(call Py3Package,dbus-python))
$(eval $(call BuildPackage,dbus-python))
