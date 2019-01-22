#
# Copyright (C) 2019 CZ.NIC z.s.p.o. (http://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=ninja
PKG_VERSION:=1.8.2

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/ninja-build/ninja/tar.gz/v$(PKG_VERSION)?
PKG_MD5SUM:=86b8700c3d0880c2b44c2ff67ce42774aaf8c28cbf57725cb881569288c1c6f4

include $(INCLUDE_DIR)/host-build.mk

HOST_CONFIGURE_ARGS := \
	--bootstrap

define Host/Compile
	cd  $(HOST_BUILD_DIR) && ./configure.py $(HOST_CONFIGURE_ARGS)
endef

define Host/Install
	$(INSTALL_BIN) $(HOST_BUILD_DIR)/ninja $(STAGING_DIR_HOST)/usr/bin/
endef

define Host/Clean
	$(call Host/Clean/Default)
endef

$(eval $(call HostBuild))
