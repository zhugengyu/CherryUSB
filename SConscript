from building import *

cwd = GetCurrentDir()
path = [cwd + '/common']
path += [cwd + '/core']
path += [cwd + '/class/cdc']
path += [cwd + '/class/msc']
path += [cwd + '/class/hid']
path += [cwd + '/class/audio']
path += [cwd + '/class/video']
path += [cwd + '/class/wireless']
path += [cwd + '/class/dfu']
path += [cwd + '/class/midi']
path += [cwd + '/class/vendor/net']
path += [cwd + '/class/vendor/serial']
src = []

LIBS    = []
LIBPATH = []
CPPDEFINES = []

# USB DEVICE
if GetDepend(['PKG_CHERRYUSB_DEVICE']):
    path += [cwd + '/osal']
    src += Glob('core/usbd_core.c')
    src += Glob('osal/usb_osal_rtthread.c')

    if GetDepend(['PKG_CHERRYUSB_DEVICE_HS']):
        CPPDEFINES+=['CONFIG_USB_HS']

    if GetDepend(['PKG_CHERRYUSB_DEVICE_FSDEV']):
        src += Glob('port/fsdev/usb_dc_fsdev.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_DWC2_ST']):
        src += Glob('port/dwc2/usb_dc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_st.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_DWC2_ESP']):
        src += Glob('port/dwc2/usb_dc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_esp.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_DWC2_AT']):
        src += Glob('port/dwc2/usb_dc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_at.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_DWC2_GD']):
        src += Glob('port/dwc2/usb_dc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_gd.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_DWC2_HC']):
        src += Glob('port/dwc2/usb_dc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_hc.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_DWC2_CUSTOM']):
        src += Glob('port/dwc2/usb_dc_dwc2.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_MUSB_ES']):
        src += Glob('port/musb/usb_dc_musb.c')
        src += Glob('port/musb/usb_glue_es.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_MUSB_SUNXI']):
        src += Glob('port/musb/usb_dc_musb.c')
        src += Glob('port/musb/usb_glue_sunxi.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_MUSB_BK']):
        src += Glob('port/musb/usb_dc_musb.c')
        src += Glob('port/musb/usb_glue_bk.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_MUSB_CUSTOM']):
        src += Glob('port/musb/usb_dc_musb.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_BL']):
        src += Glob('port/bouffalolab/usb_dc_bl.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_HPM']):
        src += Glob('port/hpm/usb_dc_hpm.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_AIC']):
        src += Glob('port/aic/usb_dc_aic.c')
        src += Glob('port/aic/usb_dc_aic_ll.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_CH32']):
        if GetDepend(['PKG_CHERRYUSB_DEVICE_HS']):
            src += Glob('port/ch32/usb_dc_usbhs.c')
        else:
            src += Glob('port/ch32/usb_dc_usbfs.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_PUSB2']):
        path += [cwd + '/port/xhci/rt-thread']
        src += Glob('port/pusb2/rt-thread/usb_dc_glue_phytium.c')
        if GetDepend(['ARCH_ARMV8']):
            LIBPATH = [cwd + '/port/pusb2']
            LIBS = ['libpusb2_dc_a64.a']
        if GetDepend(['ARCH_ARM_CORTEX_A']):
            LIBPATH = [cwd + '/port/pusb2']
            LIBS = ['libpusb2_dc_a32_softfp.a']

    if GetDepend(['PKG_CHERRYUSB_DEVICE_CDC_ACM']):
        src += Glob('class/cdc/usbd_cdc.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_HID']):
        src += Glob('class/hid/usbd_hid.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_MSC']):
        src += Glob('class/msc/usbd_msc.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_AUDIO']):
        src += Glob('class/audio/usbd_audio.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_VIDEO']):
        src += Glob('class/video/usbd_video.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_CDC_RNDIS']):
        src += Glob('class/wireless/usbd_rndis.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_CDC_ECM']):
        src += Glob('class/cdc/usbd_cdc_ecm.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_CDC_NCM']):
        src += Glob('class/cdc/usbd_cdc_ncm.c')
    if GetDepend(['PKG_CHERRYUSB_USING_DFU']):
        src += Glob('class/dfu/usbd_dfu.c')

    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_CDC_ACM']):
        src += Glob('demo/cdc_acm_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_MSC']):
        src += Glob('demo/msc_ram_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_HID_MOUSE']):
        src += Glob('demo/hid_mouse_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_HID_KEYBOARD']):
        src += Glob('demo/hid_keyboard_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_HID_CUSTOM']):
        src += Glob('demo/hid_custom_inout_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_VIDEO']):
        src += Glob('demo/video_static_mjpeg_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_AUDIO_V1_MIC_SPEAKER']):
        src += Glob('demo/audio_v1_mic_speaker_multichan_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_AUDIO_V2_MIC_SPEAKER']):
        src += Glob('demo/audio_v2_mic_speaker_multichan_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_CDC_RNDIS']):
        src += Glob('demo/cdc_rndis_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_CDC_ECM']):
        src += Glob('demo/cdc_ecm_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_CDC_NCM']):
        src += Glob('demo/cdc_ncm_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_CDC_ACM_MSC']):
        src += Glob('demo/cdc_acm_msc_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_CDC_ACM_MSC_HID']):
        src += Glob('demo/cdc_acm_hid_msc_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_WINUSBV1']):
        src += Glob('demo/winusb1.0_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_WINUSBV2_CDC']):
        src += Glob('demo/winusb2.0_cdc_template.c')
    if GetDepend(['PKG_CHERRYUSB_DEVICE_TEMPLATE_WINUSBV2_HID']):
        src += Glob('demo/winusb2.0_hid_template.c')

# USB HOST
if GetDepend(['PKG_CHERRYUSB_HOST']):
    path += [cwd + '/class/hub']
    src += Glob('core/usbh_core.c')
    src += Glob('class/hub/usbh_hub.c')
    src += Glob('osal/usb_osal_rtthread.c')

    if GetDepend(['PKG_CHERRYUSB_HOST_EHCI_BL']):
        src += Glob('port/ehci/usb_hc_ehci.c')
        src += Glob('port/ehci/usb_glue_bouffalo.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_EHCI_HPM']):
        src += Glob('port/ehci/usb_hc_ehci.c')
        src += Glob('port/ehci/usb_glue_hpm.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_EHCI_AIC']):
        path += [cwd + '/port/ehci']
        path += [cwd + '/port/ohci']
        src += Glob('port/ehci/usb_hc_ehci.c')
        src += Glob('port/ehci/usb_glue_aic.c')
        src += Glob('port/ohci/usb_hc_ohci.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_EHCI_NUVOTON_NUC980']):
        src += Glob('port/ehci/usb_hc_ehci.c')
        src += Glob('port/ehci/usb_glue_nuc980.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_EHCI_NUVOTON_MA35D0']):
        src += Glob('port/ehci/usb_hc_ehci.c')
        src += Glob('port/ehci/usb_glue_ma35d0.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_EHCI_CUSTOM']):
        src += Glob('port/ehci/usb_hc_ehci.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_DWC2_ST']):
        src += Glob('port/dwc2/usb_hc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_st.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_DWC2_ESP']):
        src += Glob('port/dwc2/usb_hc_dwc2.c')
        src += Glob('port/dwc2/usb_glue_esp.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_DWC2_CUSTOM']):
        src += Glob('port/dwc2/usb_hc_dwc2.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_MUSB_STANDARD']):
        src += Glob('port/musb/usb_hc_musb.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_MUSB_ES']):
        src += Glob('port/musb/usb_hc_musb.c')
        src += Glob('port/musb/usb_glue_es.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_MUSB_SUNXI']):
        src += Glob('port/musb/usb_hc_musb.c')
        src += Glob('port/musb/usb_glue_sunxi.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_MUSB_BK']):
        src += Glob('port/musb/usb_hc_musb.c')
        src += Glob('port/musb/usb_glue_bk.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_MUSB_CUSTOM']):
        src += Glob('port/musb/usb_hc_musb.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_PUSB2']):
        path += [cwd + '/port/pusb2/rt-thread']
        src += Glob('port/pusb2/rt-thread/usb_hc_glue_phytium.c')
        if GetDepend(['ARCH_ARMV8']):
            LIBPATH = [cwd + '/port/pusb2']
            LIBS = ['libpusb2_hc_a64.a']
        if GetDepend(['ARCH_ARM_CORTEX_A']):
            LIBPATH = [cwd + '/port/pusb2']
            LIBS = ['libpusb2_hc_a32_softfp.a']

    if GetDepend(['PKG_CHERRYUSB_HOST_XHCI']):
        path += [cwd + '/port/xhci/phytium/rt-thread']
        src += Glob('port/xhci/phytium/rt-thread/usb_glue_phytium_plat.c')
        src += Glob('port/xhci/phytium/rt-thread/usb_glue_phytium.c')
        if GetDepend(['ARCH_ARMV8']):
            LIBPATH = [cwd + '/port/xhci/phytium']
            LIBS = ['libxhci_a64.a']
        if GetDepend(['ARCH_ARM_CORTEX_A']):
            LIBPATH = [cwd + '/port/xhci/phytium']
            LIBS = ['libxhci_a32_softfp.a']

    if GetDepend(['PKG_CHERRYUSB_HOST_CDC_ACM']):
        src += Glob('class/cdc/usbh_cdc_acm.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_HID']):
        src += Glob('class/hid/usbh_hid.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_MSC']):
        src += Glob('class/msc/usbh_msc.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_CDC_RNDIS']):
        src += Glob('class/wireless/usbh_rndis.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_CDC_ECM']):
        src += Glob('class/cdc/usbh_cdc_ecm.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_CDC_NCM']):
        src += Glob('class/cdc/usbh_cdc_ncm.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_VIDEO']):
        src += Glob('class/video/usbh_video.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_AUDIO']):
        src += Glob('class/audio/usbh_audio.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_BLUETOOTH']):
        src += Glob('class/wireless/usbh_bluetooth.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_ASIX']):
        src += Glob('class/vendor/net/usbh_asix.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_RTL8152']):
        src += Glob('class/vendor/net/usbh_rtl8152.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_FTDI']):
        src += Glob('class/vendor/serial/usbh_ftdi.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_CH34X']):
        src += Glob('class/vendor/serial/usbh_ch34x.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_CP210X']):
        src += Glob('class/vendor/serial/usbh_cp210x.c')
    if GetDepend(['PKG_CHERRYUSB_HOST_PL2303']):
        src += Glob('class/vendor/serial/usbh_pl2303.c')

    if GetDepend(['PKG_CHERRYUSB_HOST_TEMPLATE']):
        src += Glob('demo/usb_host.c')

    if GetDepend('RT_USING_DFS') and GetDepend(['PKG_CHERRYUSB_HOST_MSC']):
       src += Glob('platform/rtthread/usbh_dfs.c')

    if GetDepend('PKG_CHERRYUSB_HOST_CDC_ECM') \
        or GetDepend('PKG_CHERRYUSB_HOST_CDC_RNDIS') \
        or GetDepend('PKG_CHERRYUSB_HOST_CDC_NCM') \
        or GetDepend('PKG_CHERRYUSB_HOST_ASIX') \
        or GetDepend('PKG_CHERRYUSB_HOST_RTL8152'):
       src += Glob('platform/rtthread/usbh_lwip.c')

src += Glob('platform/rtthread/usb_msh.c')
src += Glob('platform/rtthread/usb_check.c')

group = DefineGroup('CherryUSB', src, depend = ['PKG_USING_CHERRYUSB'], CPPPATH = path, CPPDEFINES = CPPDEFINES)

Return('group')

