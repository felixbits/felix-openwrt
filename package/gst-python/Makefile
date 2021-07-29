include $(TOPDIR)/rules.mk

PKG_NAME:=gst-python
PKG_VERSION:=1.12.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=http://gstreamer.freedesktop.org/src/gst-python/
PKG_HASH:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/gst-python-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xf $(DL_DIR)/$(PKG_SOURCE)
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

TARGET_CFLAGS += $(FPIC)
CONFIGURE_ARGS += \
	PYTHON=python$(PYTHON3_VERSION) \
	PYTHON_LIBS="-L$(STAGING_DIR)/usr/lib -lpython$(PYTHON3_VERSION)" \
	PYTHON_INCLUDES=-I$(STAGING_DIR)/usr/include/python$(PYTHON3_VERSION) \
	PYTHON_LIB_LOC=$(STAGING_DIR)/usr/lib

define Package/gst-python
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python bindings for gstreamer
  URL:=http://gstreamer.freedesktop.org/
  DEPENDS:=+gstreamer1 +gstreamer1-plugins-base +pygobject +python3
endef

define Package/gst-python/description
  python bindings for gstreamer
endef

define Package/gst-python/install
	$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)/gi/overrides
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/gi/overrides/*.{so,la,py} \
		$(1)$(PYTHON3_PKG_DIR)/gi/overrides

	$(INSTALL_DIR) $(1)/usr/lib/gstreamer-1.0
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/gstreamer-1.0/*.{so,la} \
		$(1)/usr/lib/gstreamer-1.0

endef

$(eval $(call BuildPackage,gst-python))
