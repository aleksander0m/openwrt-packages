#
# Copyright (C) 2017 Daniel Engberg <daniel.engberg.lists@pyret.net>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=twolame
PKG_VERSION:=0.3.13
PKG_RELEASE:=1
PKG_MAINTAINER:=Aleksander Morgado <aleksander@aleksander.es>
PKG_LICENSE:=LGPL

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/aleksander0m/twolame.git
PKG_SOURCE_SUBDIR=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=3217e3178beb74ed56f7a5d92e292bb3e4ee2f94
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/twolame
  SECTION:=sound
  CATEGORY:=Sound
  TITLE:=TwoLAME
  URL:=https://github.com/njh/twolame
endef

define Package/twolame/description
  TwoLAME library
endef

define Build/Configure
        $(call Build/Configure/Default, \
        --disable-maintainer-mode \
        )
endef

define Package/twolame/install	
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/libtwolame/.libs/*.so* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/
	$(CP) $(PKG_BUILD_DIR)/libtwolame/twolame.h $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/libtwolame/.libs/*.{la,so*} $(1)/usr/lib/
endef

$(eval $(call BuildPackage,twolame))
