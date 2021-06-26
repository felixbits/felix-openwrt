#
# Copyright (C) 2021 Kishan Go <kishanpgondaliya@gmail.com>
#
# This is free software, licensed under the GPL 2 license.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libgirepository
PKG_VERSION:=1.59.5
PKG_RELEASE=1


include $(INCLUDE_DIR)/package.mk

define Package/libgirepository
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=libgirepository
  DEPENDS:=+glib2 +libffi +gobject-introspection
endef

define Package/libgirepository/description
	libgirepository
endef

define Build/Configure
endef


define Build/Compile
endef

define Build/InstallDev
	$(CP) ./files/* $(1)
endef

define Package/libgirepository/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) ./files/usr/lib/*.so* $(1)/usr/lib
endef

$(eval $(call BuildPackage,libgirepository))
