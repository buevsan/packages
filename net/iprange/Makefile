#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=iprange
PKG_VERSION:=1-1
PKG_RELEASE=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/firehol/iprange.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=71a3075774ed39e9696a76d35405c69c290a952d
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_FIXUP:=autoreconf
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk

TARGET_CFLAGS :=
CONFIGURE_ARGS+=--disable-man
#CMAKE_OPTIONS = \
#	-DCMAKE_INSTALL_PREFIX=/usr \
#	-DWITH_DEBUG=OFF \

define Build/Configure
	(cd $(PKG_BUILD_DIR); ./autogen.sh );
	$(call Build/Configure/Default)
endef

define Package/iprange
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Utility to calc and optimize ip address ranges and lists 
  URL:=http://firehol.org
  DEPENDS:= +libc
  MAINTAINER:=Alexander Buev san@zzz.spb.ru
endef

define Package/iprange/description
  ipcalc - Utility to calc and optimize ip address ranges and lists
endef

define Package/iprange/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/iprange \
		$(1)/usr/bin
endef

$(eval $(call BuildPackage,iprange))
