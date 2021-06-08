#
# Copyright (C) 2021 Kishan Go <kishanpgondaliya@gmail.com>
#
# This is free software, licensed under the GPL 2 license.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=gobject-introspection
PKG_VERSION:=1.59.5
PKG_RELEASE=1


include $(INCLUDE_DIR)/package.mk

define Package/gobject-introspection
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=gobject-introspection
endef

define Package/gobject-introspection/description
	gobject-introspection
endef

define Build/Configure
endef


define Build/Compile
endef

define Build/InstallDev
	$(CP) ./files/* $(1)
endef

define Package/gobject-introspection/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) ./files/usr/lib/girepository-1.0 $(1)/usr/lib
endef

$(eval $(call BuildPackage,gobject-introspection))
