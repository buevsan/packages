#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=obfsclient
PKG_VERSION:=0.0.2-git-a7aedb
PKG_RELEASE=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Yawning/obfsclient.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=a7aedbc77d6714ad32c042a51334e541da8d6a41
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_FIXUP:=autoreconf
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/obfsclient
  SECTION:=net
  CATEGORY:=Network
  TITLE:=A C++11 obfs2/3 Tor managed pluggable transport client
  URL:=https://github.com/Yawning/obfsclient
  DEPENDS:= +libstdcpp +libopenssl +liballium-1.0 +libevent2
  MAINTAINER:=Alexander Buev san@zzz.spb.ru
endef

define Package/obfsclient/description
  obfsclient - A C++11 obfs2/3 Tor managed pluggable transport client
endef

define Package/obfsclient/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/obfsclient \
		$(1)/usr/bin
endef

$(eval $(call BuildPackage,obfsclient))
