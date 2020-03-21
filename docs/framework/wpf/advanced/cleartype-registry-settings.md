---
title: ClearType 注册表设置
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: bedd99fcf9b4ca1d10b4c24d7cff9de320e6fd12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186178"
---
# <a name="cleartype-registry-settings"></a><span data-ttu-id="2cbca-102">ClearType 注册表设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-102">ClearType Registry Settings</span></span>
<span data-ttu-id="2cbca-103">本主题概述了 WPF 应用程序使用的 Microsoft ClearType 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-103">This topic provides an overview of the Microsoft ClearType registry settings that are used by WPF applications.</span></span>  

<a name="overview"></a>
## <a name="technology-overview"></a><span data-ttu-id="2cbca-104">技术概述</span><span class="sxs-lookup"><span data-stu-id="2cbca-104">Technology Overview</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2cbca-105">向显示设备呈现文本的应用程序使用 ClearType 功能提供增强的阅读体验。</span><span class="sxs-lookup"><span data-stu-id="2cbca-105">applications that render text to a display device use ClearType features to provide an enhanced reading experience.</span></span> <span data-ttu-id="2cbca-106">ClearType 是 Microsoft 开发的一种软件技术，可提高现有 LCD（液晶显示器）文本的可读性，例如笔记本电脑屏幕、袖珍 PC 屏幕和平板显示器。</span><span class="sxs-lookup"><span data-stu-id="2cbca-106">ClearType is a software technology developed by Microsoft that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="2cbca-107">ClearType 的工作原理是访问 LCD 屏幕每个像素中的单个垂直颜色条纹元素。</span><span class="sxs-lookup"><span data-stu-id="2cbca-107">ClearType works by accessing the individual vertical color stripe elements in every pixel of an LCD screen.</span></span> <span data-ttu-id="2cbca-108">有关清除类型的详细信息，请参阅[清除类型概述](cleartype-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2cbca-108">For more information on ClearType, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 <span data-ttu-id="2cbca-109">在各种显示设备上查看时，使用 ClearType 呈现的文本可能会明显不同。</span><span class="sxs-lookup"><span data-stu-id="2cbca-109">Text that is rendered with ClearType can appear significantly different when viewed on various display devices.</span></span> <span data-ttu-id="2cbca-110">例如，少量监视器以蓝色、绿色、红色顺序实现颜色条纹元素，而不是更常见的红色、绿色、蓝色 （RGB） 顺序。</span><span class="sxs-lookup"><span data-stu-id="2cbca-110">For example, a small number of monitors implement the color stripe elements in blue, green, red order rather than the more common red, green, blue (RGB) order.</span></span>  
  
 <span data-ttu-id="2cbca-111">当具有不同颜色敏感度级别的个人查看时，使用 ClearType 呈现的文本也会出现显著差异。</span><span class="sxs-lookup"><span data-stu-id="2cbca-111">Text that is rendered with ClearType can also appear significantly different when viewed by individuals with varying levels of color sensitivity.</span></span> <span data-ttu-id="2cbca-112">某些人能够比别人更擅长发觉颜色的微小差异。</span><span class="sxs-lookup"><span data-stu-id="2cbca-112">Some individuals can detect slight differences in color better than others.</span></span>  
  
 <span data-ttu-id="2cbca-113">在每种情况下，都需要修改 ClearType 功能，以便为每个人提供最佳的阅读体验。</span><span class="sxs-lookup"><span data-stu-id="2cbca-113">In each of these cases, ClearType features need to be modified in order to provide the best reading experience for each individual.</span></span>  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a><span data-ttu-id="2cbca-114">注册表设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2cbca-115">指定用于控制 ClearType 功能的四个注册表设置：</span><span class="sxs-lookup"><span data-stu-id="2cbca-115">specifies four registry settings for controlling ClearType features:</span></span>  
  
|<span data-ttu-id="2cbca-116">设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-116">Setting</span></span>|<span data-ttu-id="2cbca-117">说明</span><span class="sxs-lookup"><span data-stu-id="2cbca-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cbca-118">清除类型级别</span><span class="sxs-lookup"><span data-stu-id="2cbca-118">ClearType level</span></span>|<span data-ttu-id="2cbca-119">描述清晰类型颜色清晰度级别。</span><span class="sxs-lookup"><span data-stu-id="2cbca-119">Describes the level of ClearType color clarity.</span></span>|  
|<span data-ttu-id="2cbca-120">伽马级别</span><span class="sxs-lookup"><span data-stu-id="2cbca-120">Gamma level</span></span>|<span data-ttu-id="2cbca-121">描述显示设备的像素颜色组件的级别。</span><span class="sxs-lookup"><span data-stu-id="2cbca-121">Describes the level of the pixel color component for a display device.</span></span>|  
|<span data-ttu-id="2cbca-122">像素结构</span><span class="sxs-lookup"><span data-stu-id="2cbca-122">Pixel structure</span></span>|<span data-ttu-id="2cbca-123">描述显示设备的像素排列。</span><span class="sxs-lookup"><span data-stu-id="2cbca-123">Describes the arrangement of pixels for a display device.</span></span>|  
|<span data-ttu-id="2cbca-124">文本对比度级别</span><span class="sxs-lookup"><span data-stu-id="2cbca-124">Text contrast level</span></span>|<span data-ttu-id="2cbca-125">描述显示文本的对比度级别。</span><span class="sxs-lookup"><span data-stu-id="2cbca-125">Describes the level of contrast for displayed text.</span></span>|  
  
 <span data-ttu-id="2cbca-126">这些设置可以通过外部配置实用程序访问，该实用程序知道如何引用已识别[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的 ClearType 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-126">These settings can be accessed by an external configuration utility that knows how to reference the identified [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType registry settings.</span></span> <span data-ttu-id="2cbca-127">还可以通过使用 Windows 注册表编辑器直接访问这些值来创建或修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-127">These settings can also be created or modified by accessing the values directly by using the Windows Registry Editor.</span></span>  
  
 <span data-ttu-id="2cbca-128">如果未设置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType 注册表设置（这是默认状态），[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序将查询 Windows 系统参数信息以进行字体平滑设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-128">If the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType registry settings are not set (which is the default state), the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application queries the Windows system parameters information for font smoothing settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2cbca-129">有关枚举显示设备名称的信息，请参阅`SystemParametersInfo`Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="2cbca-129">For information on enumerating display device names, see the `SystemParametersInfo`Win32 function.</span></span>  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a><span data-ttu-id="2cbca-130">ClearType 级别</span><span class="sxs-lookup"><span data-stu-id="2cbca-130">ClearType Level</span></span>  
 <span data-ttu-id="2cbca-131">ClearType 级别允许您根据个人的颜色敏感度和感知来调整文本的呈现。</span><span class="sxs-lookup"><span data-stu-id="2cbca-131">The ClearType level allows you to adjust the rendering of text based on the color sensitivity and perception of an individual.</span></span> <span data-ttu-id="2cbca-132">对于某些个人，在最高级别使用 ClearType 的文本的呈现不会产生最佳的阅读体验。</span><span class="sxs-lookup"><span data-stu-id="2cbca-132">For some individuals, the rendering of text that uses ClearType at its highest level does not produce the best reading experience.</span></span>  
  
 <span data-ttu-id="2cbca-133">ClearType 级别是一个介于 0 到 100 的整数值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-133">The ClearType level is an integer value that ranges from 0 to 100.</span></span> <span data-ttu-id="2cbca-134">默认级别为 100，这意味着 ClearType 使用显示设备的颜色条带元素的最大功能。</span><span class="sxs-lookup"><span data-stu-id="2cbca-134">The default level is 100, which means ClearType uses the maximum capability of the color stripe elements of the display device.</span></span> <span data-ttu-id="2cbca-135">但是，ClearType 级别为 0 会将文本渲染为灰色比例。</span><span class="sxs-lookup"><span data-stu-id="2cbca-135">However, a ClearType level of 0 renders text as gray scale.</span></span> <span data-ttu-id="2cbca-136">通过将 ClearType 级别设置为介于 0 和 100 之间，可以创建适合个人颜色敏感度的中间级别。</span><span class="sxs-lookup"><span data-stu-id="2cbca-136">By setting the ClearType level somewhere between 0 and 100, you can create an intermediate level that is suitable to an individual's color sensitivity.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="2cbca-137">注册表设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-137">Registry Setting</span></span>  
 <span data-ttu-id="2cbca-138">ClearType 级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：</span><span class="sxs-lookup"><span data-stu-id="2cbca-138">The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="2cbca-139">对于用户的每个显示设备名称，将定义一`ClearTypeLevel`个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-139">For each display device name for a user, a `ClearTypeLevel` DWORD value is defined.</span></span> <span data-ttu-id="2cbca-140">以下屏幕截图显示了 ClearType 级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-140">The following screenshot shows the Registry Editor setting for the ClearType level.</span></span>  
  
 ![清除注册表编辑器中的设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2cbca-142">应用程序以两种模式之一呈现文本，带和没有 ClearType。</span><span class="sxs-lookup"><span data-stu-id="2cbca-142">applications render text in one of either two modes, with and without ClearType.</span></span> <span data-ttu-id="2cbca-143">在未显示 ClearType 的情况下呈现文本时，它称为灰度渲染。</span><span class="sxs-lookup"><span data-stu-id="2cbca-143">When text is rendered without ClearType, it is referred to as gray scale rendering.</span></span>  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a><span data-ttu-id="2cbca-144">伽马级别</span><span class="sxs-lookup"><span data-stu-id="2cbca-144">Gamma Level</span></span>  
 <span data-ttu-id="2cbca-145">伽玛级别指的是像素值和亮度之间的非线性关系。</span><span class="sxs-lookup"><span data-stu-id="2cbca-145">The gamma level refers to the nonlinear relationship between a pixel value and luminance.</span></span> <span data-ttu-id="2cbca-146">伽玛级别设置应对应于显示设备的物理特性；否则呈现的输出中可能会出现失真。</span><span class="sxs-lookup"><span data-stu-id="2cbca-146">The gamma level setting should correspond to the physical characteristics of the display device; otherwise, distortions in rendered output may occur.</span></span> <span data-ttu-id="2cbca-147">例如，文本可能显得过于宽或太窄，或者颜色条纹可能出现在字形垂直茎的边缘。</span><span class="sxs-lookup"><span data-stu-id="2cbca-147">For example, text may appear too wide or too narrow, or color fringes may appear on the edges of vertical stems of glyphs.</span></span>  
  
 <span data-ttu-id="2cbca-148">伽马级别是一个介于 1000 到 2200 之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-148">The gamma level is an integer value that ranges from 1000 to 2200.</span></span> <span data-ttu-id="2cbca-149">默认级别为 1900。</span><span class="sxs-lookup"><span data-stu-id="2cbca-149">The default level is 1900.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="2cbca-150">注册表设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-150">Registry Setting</span></span>  
 <span data-ttu-id="2cbca-151">伽马级别的注册表设置位置是对应于特定显示设备名称的本地计算机设置：</span><span class="sxs-lookup"><span data-stu-id="2cbca-151">The registry setting location for the gamma level is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="2cbca-152">对于用户的每个显示设备名称，将定义一`GammaLevel`个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-152">For each display device name for a user, a `GammaLevel` DWORD value is defined.</span></span> <span data-ttu-id="2cbca-153">以下屏幕快照显示了伽马级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-153">The following screenshot shows the Registry Editor setting for the gamma level.</span></span>  
  
 ![清除注册表编辑器中的伽马级设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a><span data-ttu-id="2cbca-155">像素结构</span><span class="sxs-lookup"><span data-stu-id="2cbca-155">Pixel Structure</span></span>  
 <span data-ttu-id="2cbca-156">像素结构描述构成显示设备的像素的类型。</span><span class="sxs-lookup"><span data-stu-id="2cbca-156">The pixel structure describes the type of pixels that make up a display device.</span></span> <span data-ttu-id="2cbca-157">像素结构定义为三种类型之一：</span><span class="sxs-lookup"><span data-stu-id="2cbca-157">The pixel structure is defined as one of three types:</span></span>  
  
|<span data-ttu-id="2cbca-158">类型</span><span class="sxs-lookup"><span data-stu-id="2cbca-158">Type</span></span>|<span data-ttu-id="2cbca-159">值</span><span class="sxs-lookup"><span data-stu-id="2cbca-159">Value</span></span>|<span data-ttu-id="2cbca-160">说明</span><span class="sxs-lookup"><span data-stu-id="2cbca-160">Description</span></span>|  
|----------|-----------|-----------------|  
|<span data-ttu-id="2cbca-161">平面</span><span class="sxs-lookup"><span data-stu-id="2cbca-161">Flat</span></span>|<span data-ttu-id="2cbca-162">0</span><span class="sxs-lookup"><span data-stu-id="2cbca-162">0</span></span>|<span data-ttu-id="2cbca-163">显示设备没有像素结构。</span><span class="sxs-lookup"><span data-stu-id="2cbca-163">The display device has no pixel structure.</span></span> <span data-ttu-id="2cbca-164">这意味着每种颜色的光源均匀分布在像素区域上，称为灰度呈现。</span><span class="sxs-lookup"><span data-stu-id="2cbca-164">This means that light sources for each color are spread equally on the pixel area—this is referred to as gray scale rendering.</span></span> <span data-ttu-id="2cbca-165">这是标准显示设备的工作方式。</span><span class="sxs-lookup"><span data-stu-id="2cbca-165">This is how a standard display device works.</span></span> <span data-ttu-id="2cbca-166">ClearType 永远不会应用于渲染的文本。</span><span class="sxs-lookup"><span data-stu-id="2cbca-166">ClearType is never applied to the rendered text.</span></span>|  
|<span data-ttu-id="2cbca-167">RGB</span><span class="sxs-lookup"><span data-stu-id="2cbca-167">RGB</span></span>|<span data-ttu-id="2cbca-168">1</span><span class="sxs-lookup"><span data-stu-id="2cbca-168">1</span></span>|<span data-ttu-id="2cbca-169">显示设备的像素由三种色条按以下顺序构成：红色、绿色和蓝色。</span><span class="sxs-lookup"><span data-stu-id="2cbca-169">The display device has pixels that consist of three stripes in the following order: red, green, and blue.</span></span> <span data-ttu-id="2cbca-170">清除类型应用于渲染的文本。</span><span class="sxs-lookup"><span data-stu-id="2cbca-170">ClearType is applied to the rendered text.</span></span>|  
|<span data-ttu-id="2cbca-171">BGR</span><span class="sxs-lookup"><span data-stu-id="2cbca-171">BGR</span></span>|<span data-ttu-id="2cbca-172">2</span><span class="sxs-lookup"><span data-stu-id="2cbca-172">2</span></span>|<span data-ttu-id="2cbca-173">显示设备的像素由三种色条按以下顺序构成：蓝色、绿色和红色。</span><span class="sxs-lookup"><span data-stu-id="2cbca-173">The display device has pixels that consist of three stripes in the following order: blue, green, and red.</span></span> <span data-ttu-id="2cbca-174">清除类型应用于渲染的文本。</span><span class="sxs-lookup"><span data-stu-id="2cbca-174">ClearType is applied to the rendered text.</span></span> <span data-ttu-id="2cbca-175">注意该顺序与 RGB 类型相反。</span><span class="sxs-lookup"><span data-stu-id="2cbca-175">Notice how the order is inverted from the RGB type.</span></span>|  
  
 <span data-ttu-id="2cbca-176">像素结构对应于 0 到 2 之间的一个整数值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-176">The pixel structure corresponds to an integer value that ranges from 0 to 2.</span></span> <span data-ttu-id="2cbca-177">默认级别为 0，表示平面像素结构。</span><span class="sxs-lookup"><span data-stu-id="2cbca-177">The default level is 0, which represents a flat pixel structure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2cbca-178">有关枚举显示设备名称的信息，请参阅`EnumDisplayDevices`Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="2cbca-178">For information on enumerating display device names, see the `EnumDisplayDevices`Win32 function.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="2cbca-179">注册表设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-179">Registry Setting</span></span>  
 <span data-ttu-id="2cbca-180">像素结构的注册表设置位置是对应于特定显示设备名称的本地计算机设置：</span><span class="sxs-lookup"><span data-stu-id="2cbca-180">The registry setting location for the pixel structure is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="2cbca-181">对于用户的每个显示设备名称，将定义一`PixelStructure`个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-181">For each display device name for a user, a `PixelStructure` DWORD value is defined.</span></span> <span data-ttu-id="2cbca-182">以下屏幕快照显示了像素结构的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-182">The following screenshot shows the Registry Editor setting for the pixel structure.</span></span>  
  
 ![清除注册表编辑器中的伽马级设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a><span data-ttu-id="2cbca-184">文本对比度级别</span><span class="sxs-lookup"><span data-stu-id="2cbca-184">Text Contrast Level</span></span>  
 <span data-ttu-id="2cbca-185">通过文本对比度级别可以根据字形的主体宽度来调整文本的呈现。</span><span class="sxs-lookup"><span data-stu-id="2cbca-185">The text contrast level allows you to adjust the rendering of text based on the stem widths of glyphs.</span></span> <span data-ttu-id="2cbca-186">文本对比度级别是一个 0 到 6 之间的整数值 - 整数值越大，主体就越宽。</span><span class="sxs-lookup"><span data-stu-id="2cbca-186">The text contrast level is an integer value that ranges from 0 to 6—the larger the integer value, the wider the stem.</span></span> <span data-ttu-id="2cbca-187">默认级别为 1。</span><span class="sxs-lookup"><span data-stu-id="2cbca-187">The default level is 1.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="2cbca-188">注册表设置</span><span class="sxs-lookup"><span data-stu-id="2cbca-188">Registry Setting</span></span>  
 <span data-ttu-id="2cbca-189">文本对比度级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：</span><span class="sxs-lookup"><span data-stu-id="2cbca-189">The registry setting location for the text contrast level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="2cbca-190">对于用户的每个显示设备名称，将定义一`TextContrastLevel`个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="2cbca-190">For each display device name for a user, a `TextContrastLevel` DWORD value is defined.</span></span> <span data-ttu-id="2cbca-191">以下屏幕快照显示了文本对比度级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="2cbca-191">The following screenshot shows the Registry Editor setting for the text contrast level.</span></span>  
  
 ![清除注册表编辑器中的设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a><span data-ttu-id="2cbca-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cbca-193">See also</span></span>

- [<span data-ttu-id="2cbca-194">ClearType 概述</span><span class="sxs-lookup"><span data-stu-id="2cbca-194">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="2cbca-195">ClearType 抗锯齿</span><span class="sxs-lookup"><span data-stu-id="2cbca-195">ClearType Antialiasing</span></span>](/windows/desktop/gdi/cleartype-antialiasing)
