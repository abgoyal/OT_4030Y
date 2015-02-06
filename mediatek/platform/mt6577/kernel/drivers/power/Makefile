obj-$(CONFIG_MTK_PMIC)          += pmic_mt6329.o pmic_mt6329_bank1.o upmu_common.o

ifeq (true,$(strip $(TARGET_BUILD_MMITEST)))
    EXTRA_CFLAGS += -DBATT_ID_CHECK_SUPPORT=0 -DBATT_TEMP_FOR_MINI=1
else
    EXTRA_CFLAGS += -DBATT_ID_CHECK_SUPPORT=1 -DBATT_TEMP_FOR_MINI=0
endif

ifeq ($(MTK_NCP1851_SUPPORT),yes) 
    obj-$(CONFIG_MTK_SMART_BATTERY) += mt_battery_tbl.o mt_fuel_gauge_tbl.o ncp1851.o
else
    ifeq ($(MTK_FAN5405_SUPPORT),yes)
        obj-$(CONFIG_MTK_SMART_BATTERY) += mt_battery_fan5405.o mt_fuel_gauge.o fan5405.o
    else
        obj-$(CONFIG_MTK_SMART_BATTERY) += mt_battery.o mt_fuel_gauge.o
    endif
endif
