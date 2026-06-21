set(CONFIG_LIBRARY mcu_bridge_cfg)

# create mcu_bridge_cfg library
add_library(${CONFIG_LIBRARY} INTERFACE)

# Allow parent application to inject its own configuration directory
if(DEFINED MCU_BRIDGE_CONFIG_DIR)
    target_include_directories(
        ${CONFIG_LIBRARY}
        INTERFACE ${MCU_BRIDGE_CONFIG_DIR}
    )
else()
    target_include_directories(
        ${CONFIG_LIBRARY}
        INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
    )
endif()
