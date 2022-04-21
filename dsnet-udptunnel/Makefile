#
# Copyright (C) 2022 Arınç ÜNAL
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=dsnet-udptunnel
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/dsnet/udptunnel
PKG_SOURCE_VERSION:=0230d34fb1b5d10cb73217d93e41e24e8e42b547
PKG_MIRROR_HASH:=25d4e83d4e3425f992df9ef74afabeebc8298c0765e3aa27fdfa316c52bfb252

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Arınç ÜNAL <arinc.unal@arinc9.com>

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

GO_PKG:=github.com/dsnet/udptunnel

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/golang/golang-package.mk

define Package/dsnet-udptunnel
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Daemon for creating a simple VPN over UDP.
  DEPENDS:=$(GO_ARCH_DEPENDS)
endef

define Package/dsnet-udptunnel/install
	$(call GoPackage/Package/Install/Bin,$(PKG_INSTALL_DIR))

	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/udptunnel $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) files/dsnet-udptunnel.init $(1)/etc/init.d/dsnet-udptunnel
endef

$(eval $(call GoBinPackage,dsnet-udptunnel))
$(eval $(call BuildPackage,dsnet-udptunnel))
