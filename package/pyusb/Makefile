include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_NAME:=pyusb
PKG_VERSION:=1.1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pyusb
PKG_HASH:=7d449ad916ce58aff60b89aae0b65ac130f289c24d6a5b7b317742eccffafc38

PKG_BUILD_DIR:=$(BUILD_DIR)/pyusb-$(PKG_VERSION)
PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

PKG_BUILD_DEPENDS:=python3

define Package/pyusb
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=pyusb
  DEPENDS:=+python3-light +libusb-1.0
  VARIANT:=python3
endef

define Package/pyusb/description
  usb port python bindings
endef

$(eval $(call Py3Package,pyusb))
$(eval $(call BuildPackage,pyusb))
