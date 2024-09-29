include $(TOPDIR)/rules.mk

PKG_NAME:=hev-socks5-tproxy
PKG_VERSION:=2.5.7
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/heiher/hev-socks5-tproxy.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=2a29dc77d54c6f3cf5e264da716a8198465874da
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

include $(INCLUDE_DIR)/package.mk

define Package/hev-socks5-tproxy
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Utility to redirect tproxy traffic to socks5 server
  URL:=https://github.com/heiher/hev-socks5-tproxy
  DEPENDS:= +libc
  MAINTAINER:=Alexander Buev san@zzz.spb.ru
endef

define Package/hev-socks5-tproxy/description
  hev-socks5-tproxy - Utility to redirect tproxy traffic to socks5 server
endef

define Package/hev-socks5-tproxy/conffiles
/etc/config/hev-socks5-tproxy
/etc/hev-socks5-tproxy/
endef

define Package/hev-socks5-tproxy/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/hev-socks5-tproxy $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/hev-socks5-tproxy
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/conf/main.yml $(1)/etc/hev-socks5-tproxy/main.yml
	$(INSTALL_DIR) $(1)/etc/config/
	$(INSTALL_CONF) ./files/hev-socks5-tproxy.config $(1)/etc/config/hev-socks5-tproxy
	$(INSTALL_DIR) $(1)/etc/init.d/
	$(INSTALL_BIN) ./files/hev-socks5-tproxy.init $(1)/etc/init.d/hev-socks5-tproxy
endef

$(eval $(call BuildPackage,hev-socks5-tproxy))


