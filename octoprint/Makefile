include $(TOPDIR)/rules.mk

PKG_NAME:=octoprint
PKG_VERSION:=1.3.4
PKG_RELEASE=1

PKG_SOURCE_URL:=https://github.com/foosel/OctoPrint/archive/
PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_MIRROR_MD5SUM:=9a2d3f3835b8b1f1e8dbaae154fb20e8

PKG_MAINTAINER:=polar3d
PKG_BUILD_DEPENDS:=python python-setuptools
PKG_BUILD_DIR:=$(BUILD_DIR)/OctoPrint-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/octoprint
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=octoprint
  ABI_VERSION:=$(PKG_VERSION)
  DEPENDS:=+python-dev python-distutils python-pip
endef

define Package/octoprint/description
  OctoPrint is the snappy web interface for your 3D printer that allows you to control and monitor all aspects of your printer and print jobs, right from your browser.
endef

define Build/Compile
	$(call Build/Compile/PyMod,, \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)", \
		PKG_VERSION="$(PKG_VERSION)" \
	)
endef

#define Package/octoprint/install
#	$(INSTALL_DIR) $(1)/bin/
#	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/CuraEngine $(1)/bin/
#endef

$(eval $(call PyPackage,octoprint))
$(eval $(call BuildPackage,octoprint))
