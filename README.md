# hackintosh-efi-msi-z490-a-pro-and-corei9-10850k

OS: Venture - 13.6.3
OC: 0.9.7

## Hardware

- CPU: Intel i9-10850k Comet Lake
- iGPU: Intel UHD 630
- dGPU: RX5600 XT
- Motherboard: MSI Z490-A-PRO:
- Audio: Realtek ALC892
- Ethernet: 2.5Gbit Realtek RTL8125B-CG

## To update OC:

Use OCAT to update
- https://www.youtube.com/watch?v=iiBnU5Di5dE
- https://elitemacx86.com/threads/how-to-update-opencore.1371/

## BIOS:
Mainboard: MSI​
    Save & Exit → Restore Defaults : Yes
    Settings \ Advanced \ Integrated Peripherals → Network Stack : [Disabled]
    Settings \ Advanced \Integrated Peripherals → Intel Serial IO : [Disabled]
    Settings \ Advanced \ Integrated Graphics Configuration → DVMT Pre-Allocated : 128MB or 64MB
    Settings \ Advanced \ USB Configuration → XHCI Hand-off : [Enabled]
    Settings \ Advanced \ USB Configuration → Legacy USB Support : [Auto]
    Settings \ Advanced \ Windows OS Configuration → MSI Fast Boot : [Disabled]
    Settings \ Advanced \ Windows OS Configuration → Fast Boot : [Disabled]
    Overclocking → Extreme Memory Profile(X.M.P) : [Enabled]
    Overclocking \ CPU Features → Intel Virtualization Tech : [Enabled]
    Overclocking \ CPU Features → Intel VT-D Tech : [Disabled]
    Settings \ Boot → Boot mode select : [LEGACY+UEFI]
For use external GPU: DGPU​
    Settings \ Advanced \ Integrated Graphics Configuration → Initiate Graphic Adapter : PEG
For use external IGPU​
    Advanced \ Integrated Graphics Configuration → Initiate Graphic Adapter : IGD

Document refer: https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#intel-bios-settings
Disable
    Fast Boot
    Secure Boot
    Serial/COM Port
    Parallel Port
    VT-d (can be enabled if you set DisableIoMapper to YES)
    Compatibility Support Module (CSM) (Must be off in most cases, GPU errors/stalls like gIO are common when this option is enabled)
    Thunderbolt (For initial install, as Thunderbolt can cause issues if not setup correctly)
    Intel SGX
    Intel Platform Trust
    CFG Lock (MSR 0xE2 write protection)(This must be off, if you can't find the option then enable AppleXcpmCfgLock under Kernel -> Quirks. Your hack will not boot with CFG-Lock enabled)
#Enable
    VT-x
    Above 4G Decoding
    Hyper-Threading
    Execute Disable Bit
    EHCI/XHCI Hand-off
    OS type: Windows 8.1/10 UEFI Mode (some motherboards may require "Other OS" instead)
    DVMT Pre-Allocated(iGPU Memory): 64MB or higher
    SATA Mode: AHCI