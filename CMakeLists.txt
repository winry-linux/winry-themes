project(WinryTheme)

cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)

include(WriteBasicConfigVersionFile)
include(FeatureSummary)

find_package(ECM 1.5.0 REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR})

# Set version
set(THEME_VERSION_MAJOR 0)
set(THEME_VERSION_MINOR 1)
set(THEME_VERSION_PATCH 0)
set(THEME_VERSION_STRING "${THEME_VERSION_MAJOR}.${THEME_VERSION_MINOR}.${THEME_VERSION_PATCH}")

find_package(KF5 ${KF5_MIN_VERSION} REQUIRED COMPONENTS Plasma)
  
include(ECMInstallIcons)
include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings)
include(GenerateExportHeader)

plasma_install_package(lookandfeel org.kde.winry.desktop look-and-feel lookandfeel)

INSTALL(FILES colors/PapirusDark.colors colors/Papirus.colors DESTINATION ${DATA_INSTALL_DIR}/color-schemes/)

feature_summary(WHAT ALL INCLUDE_QUIET_PACKAGES FATAL_ON_MISSING_REQUIRED_PACKAGES)
