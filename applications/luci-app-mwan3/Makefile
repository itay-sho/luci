#
# Copyright (C) 2017 Dan Luedtke <mail@danrl.com>
#
# This is free software, licensed under the GNU General Public License v2.

include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI support for the MWAN3 MultiWAN Manager
LUCI_DEPENDS:=+luci-base +mwan3
PKG_LICENSE:=GPL-2.0
PKG_NAME:=luci-app-mwan3
PKG_RELEASE:=1

# Fork: dl12345/luci-app-mwan3, branch openwrt-25.12 (companion UI for the
# nftables mwan3 port). https://github.com/dl12345/luci-app-mwan3
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/dl12345/luci-app-mwan3
PKG_SOURCE_DATE:=2026-07-02
PKG_SOURCE_VERSION:=06d0b2ddbdf9b9c74120292153f7ce4e4ec62e40
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=Florian Eckert <fe@dev.tdt.de>

# luci.mk unconditionally sets PKG_BUILD_DIR to $(BUILD_DIR)/$(PKG_NAME)
# (no version), since it assumes a local checkout rather than a tarball
# fetch. 'override' makes our assignment immune to that later plain ':='
# in luci.mk. Uses '=' (lazy) instead of ':=' because PKG_VERSION isn't
# derived from PKG_SOURCE_VERSION until download.mk is pulled in via
# luci.mk below -- ':=' would capture it while still empty.
override PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include ../../luci.mk

# call BuildPackage - OpenWrt buildroot signature
