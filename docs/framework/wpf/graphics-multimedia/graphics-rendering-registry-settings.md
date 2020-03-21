---
title: 图形呈现注册表设置
ms.date: 03/30/2017
helpviewer_keywords:
- rendering graphics [WPF], registry settings
- rendering graphics [WPF]
- rendering graphics [WPF], troubleshooting
- troubleshooting graphics rendering [WPF]
- graphics [WPF], rendering
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
ms.openlocfilehash: 642dfdd784af4b85672cf5b0c8e60079763f4c47
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112279"
---
# <a name="graphics-rendering-registry-settings"></a><span data-ttu-id="3226a-102">图形呈现注册表设置</span><span class="sxs-lookup"><span data-stu-id="3226a-102">Graphics Rendering Registry Settings</span></span>
<span data-ttu-id="3226a-103">本主题概述了影响 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 图形呈现注册表设置。</span><span class="sxs-lookup"><span data-stu-id="3226a-103">This topic provides an overview of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics rendering registry settings that affect [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  

<a name="overview"></a>
## <a name="when-to-use-graphics-rendering-registry-settings"></a><span data-ttu-id="3226a-104">何时使用图形呈现注册表设置</span><span class="sxs-lookup"><span data-stu-id="3226a-104">When to Use Graphics Rendering Registry Settings</span></span>  
 <span data-ttu-id="3226a-105">这些注册表设置为故障排除、调试和产品支持目的而提供。</span><span class="sxs-lookup"><span data-stu-id="3226a-105">These registry settings are provided for troubleshooting, debugging, and product support purposes.</span></span> <span data-ttu-id="3226a-106">由于对注册表的更改会影响所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序，应用程序永远不应该自动或在安装期间更改这些注册表项。</span><span class="sxs-lookup"><span data-stu-id="3226a-106">Because changes to the registry affect all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, your application should never alter these registry keys automatically, or during installation.</span></span>  
  
<a name="xpdmandwddm"></a>
## <a name="what-are-xpdm-and-wddm"></a><span data-ttu-id="3226a-107">什么是 XPDM 和 WDDM？</span><span class="sxs-lookup"><span data-stu-id="3226a-107">What are XPDM and WDDM?</span></span>  
 <span data-ttu-id="3226a-108">某些图形呈现注册表设置具有不同的默认值，具体取决于视频卡使用的是 XPDM 还是 WDDM 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="3226a-108">Some of the graphics rendering registry settings have different default values, depending on whether your video card uses an XPDM or WDDM driver.</span></span> <span data-ttu-id="3226a-109">XPDM 是微软 Windows XP 显示驱动程序模型，WDDM 是 Windows 显示驱动程序模型。</span><span class="sxs-lookup"><span data-stu-id="3226a-109">XPDM is the Microsoft Windows XP Display Driver Model and WDDM is the Windows Display Driver Model.</span></span> <span data-ttu-id="3226a-110">WDDM 在运行 Windows Vista 和 Windows 7 的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="3226a-110">WDDM is available on computers running Windows Vista and Windows 7.</span></span> <span data-ttu-id="3226a-111">XPDM 在运行 Windows Vista、微软 Windows XP 和微软 Windows 服务器 2003 的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="3226a-111">XPDM is available on computers running Windows Vista, Microsoft Windows XP, and Microsoft Windows Server 2003.</span></span> <span data-ttu-id="3226a-112">有关 WDDM 的详细信息，请参阅[Windows 显示驱动程序模型 （WDDM） 设计指南](/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide)。</span><span class="sxs-lookup"><span data-stu-id="3226a-112">For more information about WDDM, see [Windows Display Driver Model (WDDM) Design Guide](/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide).</span></span>  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a><span data-ttu-id="3226a-113">注册表设置</span><span class="sxs-lookup"><span data-stu-id="3226a-113">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="3226a-114">提供了四个注册表设置来控制 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 呈现：</span><span class="sxs-lookup"><span data-stu-id="3226a-114">provides four registry settings for controlling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendering:</span></span>  
  
|<span data-ttu-id="3226a-115">设置</span><span class="sxs-lookup"><span data-stu-id="3226a-115">Setting</span></span>|<span data-ttu-id="3226a-116">说明</span><span class="sxs-lookup"><span data-stu-id="3226a-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3226a-117">**禁用硬件加速选项**</span><span class="sxs-lookup"><span data-stu-id="3226a-117">**Disable Hardware Acceleration Option**</span></span>|<span data-ttu-id="3226a-118">指定是否应启用硬件加速。</span><span class="sxs-lookup"><span data-stu-id="3226a-118">Specifies whether hardware acceleration should be enabled.</span></span>|  
|<span data-ttu-id="3226a-119">**最大多重采样值**</span><span class="sxs-lookup"><span data-stu-id="3226a-119">**Maximum Multisample Value**</span></span>|<span data-ttu-id="3226a-120">指定用于抗锯齿 3D 内容的多采样程度。</span><span class="sxs-lookup"><span data-stu-id="3226a-120">Specifies the degree of multisampling for antialiasing 3D content.</span></span>|  
|<span data-ttu-id="3226a-121">**必需的视频驱动程序日期设置**</span><span class="sxs-lookup"><span data-stu-id="3226a-121">**Required Video Driver Date Setting**</span></span>|<span data-ttu-id="3226a-122">指定系统是否对 2004 年 11 月之前发布的驱动程序禁用硬件加速。</span><span class="sxs-lookup"><span data-stu-id="3226a-122">Specifies whether the system disables hardware acceleration for drivers released before November 2004.</span></span>|  
|<span data-ttu-id="3226a-123">**使用参考光栅器选项**</span><span class="sxs-lookup"><span data-stu-id="3226a-123">**Use Reference Rasterizer Option**</span></span>|<span data-ttu-id="3226a-124">指定 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 是否应使用参考光栅器。</span><span class="sxs-lookup"><span data-stu-id="3226a-124">Specifies whether [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] should use the reference rasterizer.</span></span>|  
  
 <span data-ttu-id="3226a-125">知道如何引用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 注册表设置的任何外部配置实用工具都可以访问这些设置。</span><span class="sxs-lookup"><span data-stu-id="3226a-125">These settings can be accessed by any external configuration utility that knows how to reference the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] registry settings.</span></span> <span data-ttu-id="3226a-126">还可以通过使用 Windows 注册表编辑器直接访问这些值来创建或修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="3226a-126">These settings can also be created or modified by accessing the values directly by using the Windows Registry Editor.</span></span>  
  
<a name="disablehardwareacceleration"></a>
## <a name="disable-hardware-acceleration-option"></a><span data-ttu-id="3226a-127">禁用硬件加速选项</span><span class="sxs-lookup"><span data-stu-id="3226a-127">Disable Hardware Acceleration Option</span></span>  
  
|<span data-ttu-id="3226a-128">注册表项</span><span class="sxs-lookup"><span data-stu-id="3226a-128">Registry key</span></span>|<span data-ttu-id="3226a-129">值类型</span><span class="sxs-lookup"><span data-stu-id="3226a-129">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|<span data-ttu-id="3226a-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="3226a-130">DWORD</span></span>|  
  
 <span data-ttu-id="3226a-131">使用“禁用硬件加速选项”\*\*\*\*，可以出于调试和测试目的而关闭硬件加速。</span><span class="sxs-lookup"><span data-stu-id="3226a-131">The **disable hardware acceleration option** enables you to turn off hardware acceleration for debugging and test purposes.</span></span> <span data-ttu-id="3226a-132">查看应用程序中的呈现项目时，尝试关闭硬件加速。</span><span class="sxs-lookup"><span data-stu-id="3226a-132">When you see rendering artifacts in an application, try turning off hardware acceleration.</span></span> <span data-ttu-id="3226a-133">如果项目消失，则视频驱动程序可能有问题。</span><span class="sxs-lookup"><span data-stu-id="3226a-133">If the artifact disappears, the problem might be with your video driver.</span></span>  
  
 <span data-ttu-id="3226a-134">“禁用硬件加速选项”\*\*\*\* 是一个等于 0 或 1 的 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="3226a-134">The **disable hardware acceleration option** is a DWORD value that is either 0 or 1.</span></span> <span data-ttu-id="3226a-135">如果值为 1，表示禁用硬件加速。</span><span class="sxs-lookup"><span data-stu-id="3226a-135">A value of 1 disables hardware acceleration.</span></span> <span data-ttu-id="3226a-136">如果值为 0，表示启用硬件加速，前提是系统满足硬件加速要求；有关详细信息，请参阅[图形呈现层](../advanced/graphics-rendering-tiers.md)。</span><span class="sxs-lookup"><span data-stu-id="3226a-136">A value of 0 enables hardware acceleration, provided the system meets hardware acceleration requirements; for more information, see [Graphics Rendering Tiers](../advanced/graphics-rendering-tiers.md).</span></span>  
  
<a name="maxmultisample"></a>
## <a name="maximum-multisample-value"></a><span data-ttu-id="3226a-137">最大多重采样值</span><span class="sxs-lookup"><span data-stu-id="3226a-137">Maximum Multisample Value</span></span>  
  
|<span data-ttu-id="3226a-138">注册表项</span><span class="sxs-lookup"><span data-stu-id="3226a-138">Registry key</span></span>|<span data-ttu-id="3226a-139">值类型</span><span class="sxs-lookup"><span data-stu-id="3226a-139">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|<span data-ttu-id="3226a-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="3226a-140">DWORD</span></span>|  
  
 <span data-ttu-id="3226a-141">最大**多采样值**使您能够调整 3D 内容的最大抗锯齿量。</span><span class="sxs-lookup"><span data-stu-id="3226a-141">The **maximum multisample value** enables you to adjust the maximum amount of antialiasing of 3D content.</span></span> <span data-ttu-id="3226a-142">使用此级别可禁用 Windows Vista 中的 3D 反锯齿。</span><span class="sxs-lookup"><span data-stu-id="3226a-142">Use this level to disable 3D antialiasing in Windows Vista.</span></span>  
  
 <span data-ttu-id="3226a-143">“最大多重采样值”\*\*\*\* 是一个 DWORD 值，范围为从 0 到 16。</span><span class="sxs-lookup"><span data-stu-id="3226a-143">The **maximum multisample value** is a DWORD value that ranges from 0 to 16.</span></span> <span data-ttu-id="3226a-144">值 0 指定应禁用 3D 内容的多样本抗锯齿，如果视频卡支持，值 16 将尝试使用多达 16 倍的多采样抗锯齿。</span><span class="sxs-lookup"><span data-stu-id="3226a-144">A value of 0 specifies that multisample antialiasing of 3D content should be disabled, and a value of 16 will attempt to use up to 16x multisample antialiasing, if supported by the video card.</span></span> <span data-ttu-id="3226a-145">请注意，在使用 XPDM 驱动程序的计算机上设置此注册表项值将导致应用程序使用大量额外的视频内存，降低 3D 渲染的性能，并可能导致呈现错误和稳定性问题。</span><span class="sxs-lookup"><span data-stu-id="3226a-145">Beware that setting this registry key value on computers using XPDM drivers will cause applications to use a large amount of additional video memory, decrease the performance of 3D rendering, and has the potential to introduce rendering errors and stability problems.</span></span>  
  
 <span data-ttu-id="3226a-146">当未设置此注册表项时， [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将默认为 0（对于 XPDM 驱动程序）和 4（对于 WDDM 驱动程序）。</span><span class="sxs-lookup"><span data-stu-id="3226a-146">When this registry key is not set, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] defaults to 0 for XPDM drivers and 4 for WDDM drivers.</span></span>  
  
<a name="requiredvideodriverdatesetting"></a>
## <a name="required-video-driver-date-setting"></a><span data-ttu-id="3226a-147">必需的视频驱动程序日期设置</span><span class="sxs-lookup"><span data-stu-id="3226a-147">Required Video Driver Date Setting</span></span>  
  
|<span data-ttu-id="3226a-148">注册表项</span><span class="sxs-lookup"><span data-stu-id="3226a-148">Registry key</span></span>|<span data-ttu-id="3226a-149">值类型</span><span class="sxs-lookup"><span data-stu-id="3226a-149">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|<span data-ttu-id="3226a-150">String</span><span class="sxs-lookup"><span data-stu-id="3226a-150">String</span></span>|  
  
 <span data-ttu-id="3226a-151">2004 年 11 月，微软发布了新版本的驱动程序测试指南;在此日期之后写的驱动程序提供了更好的稳定性。</span><span class="sxs-lookup"><span data-stu-id="3226a-151">In November, 2004, Microsoft released a new version of the driver testing guidelines; the drivers written after this date offer better stability.</span></span> <span data-ttu-id="3226a-152">默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将为这些驱动程序使用硬件加速管道，并将回退到此日期之前发布的 XPDM 驱动程序的软件呈现。</span><span class="sxs-lookup"><span data-stu-id="3226a-152">By default, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] will use the hardware acceleration pipeline for these drivers and will fall back to software rendering for XPDM drivers published before this date.</span></span>  
  
 <span data-ttu-id="3226a-153">使用“必需的视频驱动程序日期设置”\*\*\*\*，可以为 XPDM 驱动程序指定最早备用日期。</span><span class="sxs-lookup"><span data-stu-id="3226a-153">The **required video driver date setting** enables you to specify an alternate minimum date for XPDM drivers.</span></span> <span data-ttu-id="3226a-154">如果确信视频驱动程序足够稳定，可支持 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，应仅指定早于 2004 年 11 月的日期。</span><span class="sxs-lookup"><span data-stu-id="3226a-154">You should only specify a date earlier than November, 2004 if you are confident that your video driver is stable enough to support [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="3226a-155">必需的视频驱动程序采用以下格式的字符串：</span><span class="sxs-lookup"><span data-stu-id="3226a-155">The required video driver setting takes a string of the following format:</span></span>  
  
| |  
|-|  
|<span data-ttu-id="3226a-156">*YYYYMM* `/` *MM* `/` *DD*</span><span class="sxs-lookup"><span data-stu-id="3226a-156">*YYYY* `/` *MM* `/` *DD*</span></span>|  
  
 <span data-ttu-id="3226a-157">其中 *YYYY* 是四位数年份，*MM* 是两位数月份，而 *DD* 是两位数日期。</span><span class="sxs-lookup"><span data-stu-id="3226a-157">Where *YYYY* is the four-digit year, *MM* is the two-digit month, and *DD* is the two digit day.</span></span> <span data-ttu-id="3226a-158">当未设置此值时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用 2004 年 11 月作为必需的视频驱动程序日期。</span><span class="sxs-lookup"><span data-stu-id="3226a-158">When this value is unset, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uses November, 2004 as its required video driver date.</span></span>  
  
<a name="usereferencerasterizeroption"></a>
## <a name="use-reference-rasterizer-option"></a><span data-ttu-id="3226a-159">使用参考光栅器选项</span><span class="sxs-lookup"><span data-stu-id="3226a-159">Use Reference Rasterizer Option</span></span>  
  
|<span data-ttu-id="3226a-160">注册表项</span><span class="sxs-lookup"><span data-stu-id="3226a-160">Registry key</span></span>|<span data-ttu-id="3226a-161">值类型</span><span class="sxs-lookup"><span data-stu-id="3226a-161">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|<span data-ttu-id="3226a-162">DWORD</span><span class="sxs-lookup"><span data-stu-id="3226a-162">DWORD</span></span>|  
  
 <span data-ttu-id="3226a-163">**使用参考栅格器选项**使您能够强制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]进入模拟硬件呈现模式进行调试：[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]进入硬件模式，但使用 Microsoft Direct3D 参考软件栅格器 d3dref9.dll，而不是实际的硬件设备。</span><span class="sxs-lookup"><span data-stu-id="3226a-163">The **use reference rasterizer option** enables you to force [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] into a simulated hardware rendering mode for debugging: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] goes into hardware mode, but uses the Microsoft Direct3D reference software rasterizer, d3dref9.dll, instead of an actual hardware device.</span></span>  
  
 <span data-ttu-id="3226a-164">参考光栅器非常缓慢，但可以绕过视频驱动程序以避免由驱动程序问题导致的任何呈现问题。</span><span class="sxs-lookup"><span data-stu-id="3226a-164">The reference rasterizer is very slow, but bypasses your video driver to avoid any rendering issues caused by driver problems.</span></span> <span data-ttu-id="3226a-165">出于此原因，可使用参考光栅器确定呈现问题是否由视频驱动程序导致。</span><span class="sxs-lookup"><span data-stu-id="3226a-165">For this reason, you can use the reference rasterizer to determine if rendering issues are caused by the video driver.</span></span> <span data-ttu-id="3226a-166">d3dref9.dll 文件必须位于应用程序可访问它的位置，如系统路径或应用程序的本地目录中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="3226a-166">The d3dref9.dll file must be in a location where the application can access it, such as in any location in the system path or in the local directory of the application.</span></span>  
  
 <span data-ttu-id="3226a-167">“使用参考光栅器选项”\*\*\*\* 采用 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="3226a-167">The **use reference rasterizer option** takes a DWORD value.</span></span> <span data-ttu-id="3226a-168">值为 0 指示不使用参考光栅器。</span><span class="sxs-lookup"><span data-stu-id="3226a-168">A value of 0 indicates that the reference rasterizer is not used.</span></span> <span data-ttu-id="3226a-169">任何其他非零值都强制 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用参考光栅器。</span><span class="sxs-lookup"><span data-stu-id="3226a-169">Any other non-zero value forces [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to use the reference rasterizer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3226a-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3226a-170">See also</span></span>

- [<span data-ttu-id="3226a-171">图形呈现层</span><span class="sxs-lookup"><span data-stu-id="3226a-171">Graphics Rendering Tiers</span></span>](../advanced/graphics-rendering-tiers.md)
- [<span data-ttu-id="3226a-172">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="3226a-172">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
