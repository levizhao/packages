#
# Copyright (C) 2009-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=zlog
PKG_VERSION:=1.2.12
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/HardySimpson/zlog/archive/
PKG_MD5SUM:=ae9b7ede5cf3a62c3092bacf37f70de4

#PKG_FIXUP:=autoreconf
#PKG_REMOVE_FILES:=aclocal.m4 GNUmakefile
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libzlog
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+libpthread
  TITLE:=A reliable pure C logging library
  URL:=https://hardysimpson.github.io/zlog/
endef

define Package/package/libzlog
  zlog is a reliable, high-performance, thread safe, flexible, clear-model, pure C logging library.
endef

#CONFIGURE_ARGS += \
#	--enable-static \
#	--enable-shared

#TARGET_LDFLAGS += \
#	-lpthread


define Build/Install
	$(call Build/Install/Default,install PREFIX=$(PKG_INSTALL_DIR))
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/include/zlog.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/lib/libzlog.{a,so*} $(1)/usr/lib/
endef

define Package/libzlog/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/lib/libzlog.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libzlog))
