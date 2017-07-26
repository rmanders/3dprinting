include $(TOPDIR)/rules.mk

PKG_NAME:=CuraEngine
PKG_VERSION:=15.04.6
PKG_RELEASE=2

PKG_SOURCE_URL:=https://github.com/Ultimaker/CuraEngine/archive/
PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_MIRROR_MD5SUM:=acadbcb77d32e30716d09624b9c6d6f1

PKG_MAINTAINER:=polar3d

include $(INCLUDE_DIR)/package.mk

define Package/cura-engine
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=CuraEngine
  ABI_VERSION:=$(PKG_VERSION)
  DEPENDS:=+libpthread libc libstdcpp
endef

define Package/cura-engine/description
  The CuraEngine is a C++ console application for 3D printing GCode generation. It has been made as a better and faster alternative to the old Skeinforge engine.
endef

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include -L$(STAGING_DIR)/usr/lib
#TARGET_LDFLAGS += -lgcc -lc -Wl,--start-group,-lc,-lgcc,--end-group
#CMAKE_OPTIONS = \
#        -DENABLE_ARCUS=OFF

define Package/cura-engine/install
	$(INSTALL_DIR) $(1)/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/CuraEngine $(1)/bin/
endef

$(eval $(call BuildPackage,cura-engine))
