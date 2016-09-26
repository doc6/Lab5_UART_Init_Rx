################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
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

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
Lab5_UART_Init_Rx.lss \

FLASH_IMAGE += \
Lab5_UART_Init_Rx.hex \

EEPROM_IMAGE += \
Lab5_UART_Init_Rx.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: Lab5_UART_Init_Rx.elf secondary-outputs

# Tool invocations
Lab5_UART_Init_Rx.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,Lab5_UART_Init_Rx.map -mmcu=atmega328p -o "Lab5_UART_Init_Rx.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

Lab5_UART_Init_Rx.lss: Lab5_UART_Init_Rx.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S Lab5_UART_Init_Rx.elf  >"Lab5_UART_Init_Rx.lss"
	@echo 'Finished building: $@'
	@echo ' '

Lab5_UART_Init_Rx.hex: Lab5_UART_Init_Rx.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex Lab5_UART_Init_Rx.elf  "Lab5_UART_Init_Rx.hex"
	@echo 'Finished building: $@'
	@echo ' '

Lab5_UART_Init_Rx.eep: Lab5_UART_Init_Rx.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex Lab5_UART_Init_Rx.elf  "Lab5_UART_Init_Rx.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: Lab5_UART_Init_Rx.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega328p Lab5_UART_Init_Rx.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) Lab5_UART_Init_Rx.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
