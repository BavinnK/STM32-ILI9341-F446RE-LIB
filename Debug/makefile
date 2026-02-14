################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (13.3.rel1)
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Drivers/STM32F4xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/ILI9341/subdir.mk
-include Core/Src/subdir.mk
<<<<<<< HEAD
=======
-include Core/MyDRIVERS/USART/subdir.mk
-include Core/MyDRIVERS/SPI/subdir.mk
-include Core/MyDRIVERS/GPIO/subdir.mk
-include Core/MyDRIVERS/DMA/subdir.mk
-include Core/MyDRIVERS/CLOCK/subdir.mk
-include Core/MyDRIVERS/ADC/subdir.mk
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

OPTIONAL_TOOL_DEPS := \
$(wildcard ../makefile.defs) \
$(wildcard ../makefile.init) \
$(wildcard ../makefile.targets) \


<<<<<<< HEAD
BUILD_ARTIFACT_NAME := TEST
=======
BUILD_ARTIFACT_NAME := test_tft
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
<<<<<<< HEAD
TEST.elf \

MAP_FILES += \
TEST.map \
=======
test_tft.elf \

MAP_FILES += \
test_tft.map \
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
<<<<<<< HEAD
TEST.list \
=======
test_tft.list \
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)


# All Target
all: main-build

# Main-build Target
<<<<<<< HEAD
main-build: TEST.elf secondary-outputs

# Tool invocations
TEST.elf TEST.map: $(OBJS) $(USER_OBJS) C:\Users\pc\Desktop\STM_PROJECTS\TEST\STM32F446RETX_FLASH.ld makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-gcc -o "TEST.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m4 -T"C:\Users\pc\Desktop\STM_PROJECTS\TEST\STM32F446RETX_FLASH.ld" --specs=nosys.specs -Wl,-Map="TEST.map" -Wl,--gc-sections -static --specs=nano.specs -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
=======
main-build: test_tft.elf secondary-outputs

# Tool invocations
test_tft.elf test_tft.map: $(OBJS) $(USER_OBJS) C:\Users\pc\Desktop\STM_PROJECTS\test_tft\STM32F446RETX_FLASH.ld makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-gcc -o "test_tft.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m4 -T"C:\Users\pc\Desktop\STM_PROJECTS\test_tft\STM32F446RETX_FLASH.ld" --specs=nosys.specs -Wl,-Map="test_tft.map" -Wl,--gc-sections -static --specs=nano.specs -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

<<<<<<< HEAD
TEST.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "TEST.list"
=======
test_tft.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "test_tft.list"
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
<<<<<<< HEAD
	-$(RM) TEST.elf TEST.list TEST.map default.size.stdout
=======
	-$(RM) default.size.stdout test_tft.elf test_tft.list test_tft.map
>>>>>>> d357943 (removed HAL completly from the ili lib exepct the hal delays)
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST)

fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

.PHONY: all clean dependents main-build fail-specified-linker-script-missing warn-no-linker-script-specified

-include ../makefile.targets
