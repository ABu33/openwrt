#
# Copyright (C) 2021 Jo-Philipp Wich <jo@mein.io>
#

include $(TOPDIR)/rules.mk

PKG_NAME:=firewall4
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/ABu33/firewall4.git
PKG_SOURCE_DATE:=2024-06-22
PKG_SOURCE_VERSION:=b096e76543b5bd32f421f7b755ef5f14492d06b6
PKG_MAINTAINER:=Jo-Philipp Wich <jo@mein.io>
PKG_LICENSE:=ISC

include $(INCLUDE_DIR)/package.mk

define Package/firewall4
  SECTION:=net
  CATEGORY:=Base system
  TITLE:=OpenWrt 4th gen firewall
  DEPENDS:= \
	+kmod-nft-core +kmod-nft-fib +kmod-nft-offload \
	+kmod-nft-nat \
	+nftables-json \
	+ucode +ucode-mod-fs +ucode-mod-ubus +ucode-mod-uci
  EXTRA_DEPENDS:=ucode (>=2022.03.22)
  PROVIDES:=uci-firewall
endef

define Package/firewall4/description
 This package provides an nftables-based implementation of the UCI firewall
 sharing the same configuration format.
endef

define Package/firewall4/conffiles
/etc/config/firewall
/etc/nftables.d/
endef

define Package/firewall4/install
	$(CP) -a $(PKG_BUILD_DIR)/root/* $(1)/
endef

define Build/Compile
endef

$(eval $(call BuildPackage,firewall4))
