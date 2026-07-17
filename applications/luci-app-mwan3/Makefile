#
# Copyright (C) 2017 Dan Luedtke <mail@danrl.com>
#
# This is free software, licensed under the GNU General Public License v2.

include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI support for the MWAN3 MultiWAN Manager
LUCI_DEPENDS:=+luci-base +mwan3
PKG_LICENSE:=GPL-2.0
PKG_NAME:=luci-app-mwan3
PKG_VERSION:=06d0b2ddbdf9b9c74120292153f7ce4e4ec62e40
PKG_RELEASE:=1

# Fork: dl12345/luci-app-mwan3, branch openwrt-25.12 (companion UI for the
# nftables mwan3 port). https://github.com/dl12345/luci-app-mwan3
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/dl12345/luci-app-mwan3/tar.gz/$(PKG_VERSION)?
PKG_HASH:=5394bb39b6c4fb07996cf537d7c01ebe63cbab0d93911b9c6be7753196a758e8

PKG_MAINTAINER:=Florian Eckert <fe@dev.tdt.de>

# luci.mk unconditionally sets PKG_BUILD_DIR to $(BUILD_DIR)/$(PKG_NAME)
# (no version), since it assumes a local checkout rather than a tarball
# fetch. 'override' makes our assignment immune to that later plain ':='
# in luci.mk, so the extracted luci-app-mwan3-$(PKG_VERSION)/ tarball
# content (from codeload) lands exactly at $(PKG_BUILD_DIR).
override PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include ../../luci.mk

# call BuildPackage - OpenWrt buildroot signature
