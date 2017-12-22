include $(TOPDIR)/rules.mk

PKG_NAME:=l3roamd
PKG_SOURCE_DATE:=2017-12-22
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/freifunk-gluon/l3roamd.git
PKG_SOURCE_VERSION:=0241e48baccc84f86dfbd6108e0f18c2d855a116

CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE:STRING=MINSIZEREL

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/l3roamd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=The layer 3 roaming daemon
  DEPENDS:=+libnl-tiny +kmod-tun +librt
endef

define Package/l3roamd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/l3roamd $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,l3roamd))
