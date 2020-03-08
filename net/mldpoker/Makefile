include $(TOPDIR)/rules.mk

PKG_NAME:=mldpoker
PKG_VERSION:=1
PKG_RELEASE:=1

PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=

PKG_SOURCE_URL:=https://github.com/T-X/mldpoker.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2019-03-08
PKG_SOURCE_VERSION:=1b14b2da34239b7954767e7a9c6c759bab3d72de
PKG_MIRROR_HASH:=skip


include $(INCLUDE_DIR)/package.mk

define Package/mldpoker
  TITLE:=A small utility that pokes sleepy devices for MLD Reports
  SECTION:=net
  CATEGORY:=Network
endef

define Package/mldpoker/description
	A small utility that pokes sleepy devices for MLD Reports

	If a host behind IFNAME newly appeared or was unresponsive for
	at least 15 seconds and now reappeared then MLD Poker sends a
	general MLDv1 Query with an MLD Maximum Query Response Delay of
	0 to it (request for an immediate, undelayed MLD Report). The
	MLD Query is sent to the target host directly via its unicast MAC
	address.

	This tool was written to work around the following two issues:

	Roaming issues with Linux <= 4.9:
	https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=a088d1d73a4bcfd7bc482f8d08375b9b665dc3e5

	Android devices being unresponsive to MLD Queries in sleep mode:
	https://github.com/freifunk-gluon/gluon/issues/1832
	https://issuetracker.google.com/issues/149630944
endef

define Package/mldpoker/install
	$(CP) ./files/* $(1)/
	$(INSTALL_DIR) $(1)/usr/sbin/
	$(CP) $(PKG_BUILD_DIR)/mldpoker $(1)/usr/sbin/mldpoker
endef

$(eval $(call BuildPackage,mldpoker))
