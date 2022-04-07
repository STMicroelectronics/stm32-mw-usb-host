---
pagetitle: Release Notes for STM32GK Firmware Package
lang: en
header-includes: <link rel="icon" type="image/x-icon" href="_htmresc/favicon.png" />
---

::: {.row}
::: {.col-sm-12 .col-lg-4}

<center>
# Release Notes for <mark>STM32Cube USB Host Library</mark>
Copyright &copy; 2015 STMicroelectronics\

[![ST logo](_htmresc/st_logo_2020.png)](https://www.st.com){.logo}
</center>

# Purpose

The USB host library comes on top of the STM32Cube™ USB host HAL driver and
offers all the APIs required to develop an USB host application.

The main USB host library features are:

 - Support of multi packet transfer features allowing the reception of big amount of data without
   splitting it into max packet size transfers.
 - Support of most common USB Class drivers (HID, CDC, MSC, MTP, AUDIO1.0)
 - Configuration files to interface with Cube HAL and change the library configuration without changing
   the library code (Read Only).
 - 32-bits aligned data structures to handle DMA based transfer in High speed modes.

Here is the list of references to user documents:

-   [UM1720](https://www.st.com/resource/en/user_manual/dm00105256-stm32cube-usb-host-library-stmicroelectronics.pdf) : STM32Cube USB host library User Manual
-   [Wiki Page](https://wiki.st.com/stm32mcu/wiki/USB_overview) : STM32Cube USB Wiki Page

:::

::: {.col-sm-12 .col-lg-8}
# Update History
::: {.collapse}
<input type="checkbox" id="collapse-section16" checked aria-hidden="true">
<label for="collapse-section16" aria-hidden="true">V3.4.1 / 04-April-2022</label>
<div>

## Main Changes

 Headline
 ---------
 Update the way to declare licenses
 Fix code spelling and improve code style
 **HID Class**
 Modify some variables names to avoid duplication versus device for HID class



</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section15" checked aria-hidden="true">
<label for="collapse-section15" aria-hidden="true">V3.4.0 / 23-Apr-2021</label>
<div>

## Main Changes

 Headline
 ---------
 **Core driver:**
 Fixes added to free RTOS resource during USB host DeInit
 CodeSpell and mcuAstlye fixes
 Multiple MisraC 2012 fixes
 **All Classes:**
 CodeSpell and mcuAstlye fixes
 Multiple MisraC 2012 fixes


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section14" checked aria-hidden="true">
<label for="collapse-section14" aria-hidden="true">V3.3.5 / 26-Jan-2021</label>
<div>

## Main Changes

 Headline
 ---------
 **Core driver:**
 Improve enumeration phase by adding some specifications requirements checks.
 Add error signaling for some out of specification device's descriptors fields.
 **MSC Class:**
 usbh_msc.c: add checking on both IN and OUT pipes construction.
 **HID Class:**
 Fix wrong keyboard key defines.


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section13" aria-hidden="true">
<label for="collapse-section13" aria-hidden="true">V3.3.4 / 08-Jan-2020</label>
<div>

## Main Changes

 Headline
 ---------
 **Core driver:**
 Improve enumeration phase and avoid silent responses.
 Add device reset trial mechanism during enumeration phase.
 **MSC Class:**
 usbh_msc.c: update max_lun field to be uint8_t instead of  uint32_t.
 **HID Class:**
 Get HID descriptor by parsing the device descriptor in order to improve interoperability with buggy devices that Stall host Get HID descriptor request.


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section12" aria-hidden="true">
<label for="collapse-section12" aria-hidden="true">V3.3.3 / 29-April-2019</label>
<div>

## Main Changes

 Headline
 ---------
 Fix misra-C 2012 high severity violations
 **Core driver:**
 usbh_core.c: Rework USB host Core process in order to improve Device connection / disconnection robustness
 **MSC Class:**
 usbh_msc.c: Update USBH_MSC_GetMaxLUN() to prevent corruption of supported LUNs
 **HID Class:**
 Prevent race between USB buffer and Application fifo buffer, this was ensured by allocating a dedicated buffer for received report
 Prevent overflow on USB buffer for devices that could have report size greater than 4bytes


</div>
:::


::: {.collapse}
<input type="checkbox" id="collapse-section11" aria-hidden="true">
<label for="collapse-section11" aria-hidden="true">V3.3.2 / 24-Jan-2019</label>
<div>

## Main Changes

 Headline
 ---------
 **Core driver:**
 usbh_core.c: fix on USBH_Deinit() API, prevent freeing pActiveClass->pData pointer during host Deinit, this is manged by the Class drivers.

</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section10" aria-hidden="true">
<label for="collapse-section10" aria-hidden="true">V3.3.1 / 09-July-2018</label>
<div>

## Main Changes

 Headline
 ---------
 Fix interoperability issue with HP mouse
 Add compatibility with FreeRTOS CMSIS V2 API changes
 Update License section and add link to get copy of ST Ultimate Liberty license SLA0044


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section9" aria-hidden="true">
<label for="collapse-section9" aria-hidden="true">V3.3.0 / 23-Jan-2018</label>
<div>

## Main Changes

 Headline
 ---------
 Update license section to Ultimate Liberty
 Update some functions to be MISRA-C 2004 compliant
 Improve USB Core enumeration state machine
 Fix Device fast plug/unplug issue
 Improve interoperability with non compliant USB devices
 Add support of Host set remote wakeup enable feature
 Fix USB Host MSC  set correct sector size
 MSC: Set correct LUN number if returned LUN number exceeds max supported value


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section8" aria-hidden="true">
<label for="collapse-section8" aria-hidden="true">V3.2.2 / 07-July-2015</label>
<div>

## Main Changes

 Headline
 ---------
 **MSC Class:**
 usbh_msc.c: Fix MSC Get Ready Delay issue


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section7" aria-hidden="true">
<label for="collapse-section7" aria-hidden="true">V3.2.1 / 26-June-2015</label>
<div>

## Main Changes

 Headline
 ---------
 **Core driver:**
 usbh_def.h: update USBH_MAX_PIPES_NBR literal definition to be conditioned by #ifndef directive, to allow application code to change its value (i.e. in the compiler preprocessor)
 **MSC Class:**
 usbh_msc.c:
 Update USBH_MSC_GetMaxLUN() to  return the correct number of supported LUNs (was returning 0xFF)
 Fix timeout calculation issue
 usbh_msc.h:
 update MAX_SUPPORTED_LUN literal definition to be conditioned by #ifndef directive, to allow application code to change its value (i.e.in the compiler preprocessor)
 **HID Class:**
 usbh_hid.h: fix HID's handle "Timer" type to uint32_t instead of uint16_t
 **MTP Class:**
 usbh_mtp.c : Fix timeout calculation issue


</div>
:::


::: {.collapse}
<input type="checkbox" id="collapse-section6" aria-hidden="true">
<label for="collapse-section6" aria-hidden="true">V3.2.0 / 04-November-2014</label>
<div>

## Main Changes

 Headline
 ---------
 Update all drivers to be C++ compliant
 Miscellaneous source code comments update
 **Core driver**
 usbh_core.c: remove HOST_IDLE state in USBH_LL_Connect() function
 **MSC class**
 Update to manage correctly older USB Keys that do not support GetMaxLun request

</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section5" aria-hidden="true">
<label for="collapse-section5" aria-hidden="true">V3.1.0 / 19-June-2014</label>
<div>

## Main Changes

 Headline
 ---------
 **Core driver**
 Add a new define USBH_PROCESS_STACK_SIZE in the usbh_conf.h file to change the default internal USB host process stack. Note that by omitting this define, the default stack size (2KB) is used
 Add a user callback to handle unrecoverable error case in the application
 Remove the wrong check on the interface descriptor index in the USBH_FindInterface() function
 **All classes**
 Update class description in files comment by adding reference to the used USB class specification revision
 **Audio, CDC and MTP classes**
 Add full RTOS support by handling state transitions through OS messages
 **HID class**
 Add new API USBH_HID_GetPollInterval() to allow user to retrieve the needed poll time (interval between two USBD_HID_SendReport())
 **Audio class**
 Add a new weak callback USBH_AUDIO_BufferEmptyCallback() to indicate the end of audio data processing on the user buffer
 **MSC class**
 Return mass storage device capacity in Bytes in the user log message instead of MBytes

</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section4" aria-hidden="true">
<label for="collapse-section4" aria-hidden="true">V3.0.0 / 18-February-2014</label>
<div>

## Main Changes

 Headline
 ---------
 Major update based on STM32Cube specification: Library Core, Classes architecture and APIs modified vs. V2.1.0, and thus the 2 versions are not compatible.
 **This version has to be used only with STM32Cube based development**


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section3" aria-hidden="true">
<label for="collapse-section3" aria-hidden="true">V2.1.0 / 19-March-2012</label>
<div>

## Main Changes

 Headline
 ---------
 Official support of STM32F4xx devices
 All source files: license disclaimer text update and add link to the License file on ST Internet
 Add ISR structure to link the low level driver to the Host library
 Change length parameter in the I/O operations to handle large amount of data
 Enhance the configuration descriptor parsing method to take into account multi interface devices
 Miscellaneous bug fix
 **HID class**
 Remove blocking even frame synchronization loop
 **MSC class**
 Handle correctly the BOT transfer with length < max length
 Handle multi sector length data in the FAT FS interface



</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section2" aria-hidden="true">
<label for="collapse-section2" aria-hidden="true">V2.0.0 /  22-July-2011</label>
<div>

## Main Changes

 Headline
 ---------
Second official version supporting STM32F105/7 and STM32F2xx devices
Add support for **STM32F2xx** devices
Add multi interface feature
Add dynamic configuration parsing
Add USBH_DeAllocate_AllChannel function in the Host channel management layer to clean up channels allocation table when de-initializing the library
Change the core layer to stop correctly the host core and free all allocated channels
Add usbh_conf.h file in the application layer to customize some user parameters


</div>
:::

::: {.collapse}
<input type="checkbox" id="collapse-section1" aria-hidden="true">
<label for="collapse-section1" aria-hidden="true">V1.0.0  / 29-November-2010</label>
<div>

## Main Changes

 Created

</div>
:::

:::
:::

<footer class="sticky">
::: {.columns}
::: {.column width="95%"}
:::
::: {.column width="5%"}
<abbr title="Based on template cx566953 version 2.1">Info</abbr>
:::
:::
</footer>
