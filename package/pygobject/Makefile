#
# Copyright (C) 2021 Kishan Go <kishanpgondaliya@gmail.com>
#
# This is free software, licensed under the GPL 2 license.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=pygobject
PKG_VERSION:=3.27.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@GNOME/$(PKG_NAME)/3.27
PKG_HASH:=ad1375fe1af9746a1e49ada604c9658c03145a3ca204ad62bd6d917208a66b20

PKG_BUILD_DIR:=$(BUILD_DIR)/pygobject-$(PKG_VERSION)
PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xf $(DL_DIR)/$(PKG_SOURCE)

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

CONFIGURE_ARGS += --enable-static --enable-shared --disable-cairo \
PYTHON_VERSION=$(PYTHON3_VERSION) \
    PYTHON_LIBS="-L$(STAGING_DIR)/usr/lib -lpython$(PYTHON3_VERSION)" \
    PYTHON_INCLUDES=-I$(STAGING_DIR)/usr/include/python$(PYTHON3_VERSION)


define Package/pygobject
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=GLib bindings for python
  DEPENDS:=+python3 +glib2 +libffi +libgirepository
endef

define Package/pygobject/description
  GLib bindings for python3
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/pygobject-3.0
	$(CP) $(PKG_BUILD_DIR)/gi/pygobject.h $(1)/usr/include/pygobject-3.0
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_BUILD_DIR)/pygobject-3.0.pc $(1)/usr/lib/pkgconfig
endef

define Package/pygobject/install
	$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)/gi
	$(CP) $(PKG_BUILD_DIR)/gi/.libs/_gi.*.so \
		$(1)$(PYTHON3_PKG_DIR)/gi
	$(CP) $(PKG_BUILD_DIR)/gi/*.py \
		$(1)$(PYTHON3_PKG_DIR)/gi
	$(foreach d,overrides _gobject repository, \
		$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)/gi/$(d); \
		$(CP) $(PKG_BUILD_DIR)/gi/$(d)/*.py \
			$(1)$(PYTHON3_PKG_DIR)/gi/$(d); \
	)
endef

$(eval $(call BuildPackage,pygobject))
