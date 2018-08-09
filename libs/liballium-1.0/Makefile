#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

API_VER:=1.0

PKG_NAME:=liballium-$(API_VER)
PKG_VERSION:=$(API_VER).0-git-5272de
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Yawning/liballium.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=5272de7361897ee6b5c969fd1eec6609d64ac13a
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_FIXUP:=autoreconf
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/liballium-$(API_VER)
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=A C Tor Pluggable Transports Utility Library
  URL:=https://github.com/Yawning/liballium
#  DEPENDS:=
  MAINTAINER:=Alexander Buev san@zzz.spb.ru
endef

define Package/liballium-$(API_VER)/description
  liballium: A C Tor Pluggable Transports Utility Library
  Yawning Angel <yawning at schwanenlied dot me>

  liballium attempts to reduce the amount of boilerplate code required to
  implement pluggable transports for Tor in C or C++.
endef

TARGET_LDFLAGS += $(FPIC)
CONFIGURE_ARGS+= 

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/allium
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/liballium-$(API_VER).so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/liballium-$(API_VER).pc $(1)/usr/lib/pkgconfig/
endef

define Package/liballium-$(API_VER)/install
  echo QQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQQ
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/liballium-$(API_VER).so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,liballium-1.0))
