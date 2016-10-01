#
# Copyright (C) 2009-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libconfig
PKG_VERSION:=1.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.hyperrealm.com/libconfig/
PKG_MD5SUM:=625f64d8d570e03275948719df8808ea

PKG_FIXUP:=autoreconf
PKG_REMOVE_FILES:=aclocal.m4 GNUmakefile
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libconfigxx
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+libstdcpp
  TITLE:=Libconfig is a simple library for processing structured configuration files
  URL:=http://www.hyperrealm.com/libconfig/
endef

define Package/package/libconfigxx
  Libconfig is very compact — a fraction of the size of the expat XML parser library. 
  This makes it well-suited for memory-constrained systems like handheld devices.
endef

CONFIGURE_ARGS += \
	--enable-static \
	--enable-shared

#TARGET_LDFLAGS += \
#	-lpthread

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libconfig.h* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libconfig*.{a,so*} $(1)/usr/lib/
endef

define Package/libconfigxx/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libconfig*.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libconfigxx))
