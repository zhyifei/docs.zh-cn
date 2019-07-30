---
title: ClearType 注册表设置
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 8f1c4415a834f7eb7c3048a89ab81de6921b7bf6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629943"
---
# <a name="cleartype-registry-settings"></a><span data-ttu-id="42e38-102">ClearType 注册表设置</span><span class="sxs-lookup"><span data-stu-id="42e38-102">ClearType Registry Settings</span></span>
<span data-ttu-id="42e38-103">本主题概述了 WPF 应用程序使用的 Microsoft ClearType 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="42e38-103">This topic provides an overview of the Microsoft ClearType registry settings that are used by WPF applications.</span></span>  

<a name="overview"></a>   
## <a name="technology-overview"></a><span data-ttu-id="42e38-104">技术概述</span><span class="sxs-lookup"><span data-stu-id="42e38-104">Technology Overview</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="42e38-105">向显示设备呈现文本的应用程序使用 ClearType 功能提供增强的阅读体验。</span><span class="sxs-lookup"><span data-stu-id="42e38-105">applications that render text to a display device use ClearType features to provide an enhanced reading experience.</span></span> <span data-ttu-id="42e38-106">ClearType 是一种由[!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]开发的软件技术, 可提高现有 lcd (液晶显示器, 如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器) 上文本的可读性。</span><span class="sxs-lookup"><span data-stu-id="42e38-106">ClearType is a software technology developed by [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="42e38-107">ClearType 通过访问 LCD 屏幕的每个像素中的各个垂直色带元素来工作。</span><span class="sxs-lookup"><span data-stu-id="42e38-107">ClearType works by accessing the individual vertical color stripe elements in every pixel of an LCD screen.</span></span> <span data-ttu-id="42e38-108">有关 ClearType 的详细信息, 请参阅[Cleartype 概述](cleartype-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="42e38-108">For more information on ClearType, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 <span data-ttu-id="42e38-109">当在各种显示设备上查看时, 用 ClearType 呈现的文本可能出现明显不同。</span><span class="sxs-lookup"><span data-stu-id="42e38-109">Text that is rendered with ClearType can appear significantly different when viewed on various display devices.</span></span> <span data-ttu-id="42e38-110">例如, 少量监视器以蓝色、绿色、红色顺序而不是更常见的红色、绿色、蓝色 ( [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) 顺序实现颜色条带元素。</span><span class="sxs-lookup"><span data-stu-id="42e38-110">For example, a small number of monitors implement the color stripe elements in blue, green, red order rather than the more common red, green, blue (    [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) order.</span></span>  
  
 <span data-ttu-id="42e38-111">使用 ClearType 呈现的文本在由具有不同级别的颜色敏感度的个人观看时, 还会显得大不相同。</span><span class="sxs-lookup"><span data-stu-id="42e38-111">Text that is rendered with ClearType can also appear significantly different when viewed by individuals with varying levels of color sensitivity.</span></span> <span data-ttu-id="42e38-112">某些人能够比别人更擅长发觉颜色的微小差异。</span><span class="sxs-lookup"><span data-stu-id="42e38-112">Some individuals can detect slight differences in color better than others.</span></span>  
  
 <span data-ttu-id="42e38-113">在上述每种情况下, 都需要修改 ClearType 功能, 以便为每个人提供最佳阅读体验。</span><span class="sxs-lookup"><span data-stu-id="42e38-113">In each of these cases, ClearType features need to be modified in order to provide the best reading experience for each individual.</span></span>  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a><span data-ttu-id="42e38-114">注册表设置</span><span class="sxs-lookup"><span data-stu-id="42e38-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="42e38-115">指定用于控制 ClearType 功能的四个注册表设置:</span><span class="sxs-lookup"><span data-stu-id="42e38-115">specifies four registry settings for controlling ClearType features:</span></span>  
  
|<span data-ttu-id="42e38-116">设置</span><span class="sxs-lookup"><span data-stu-id="42e38-116">Setting</span></span>|<span data-ttu-id="42e38-117">描述</span><span class="sxs-lookup"><span data-stu-id="42e38-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42e38-118">ClearType 级别</span><span class="sxs-lookup"><span data-stu-id="42e38-118">ClearType level</span></span>|<span data-ttu-id="42e38-119">描述 ClearType 颜色清晰度的级别。</span><span class="sxs-lookup"><span data-stu-id="42e38-119">Describes the level of ClearType color clarity.</span></span>|  
|<span data-ttu-id="42e38-120">伽马级别</span><span class="sxs-lookup"><span data-stu-id="42e38-120">Gamma level</span></span>|<span data-ttu-id="42e38-121">描述显示设备的像素颜色组件的级别。</span><span class="sxs-lookup"><span data-stu-id="42e38-121">Describes the level of the pixel color component for a display device.</span></span>|  
|<span data-ttu-id="42e38-122">像素结构</span><span class="sxs-lookup"><span data-stu-id="42e38-122">Pixel structure</span></span>|<span data-ttu-id="42e38-123">描述显示设备的像素排列。</span><span class="sxs-lookup"><span data-stu-id="42e38-123">Describes the arrangement of pixels for a display device.</span></span>|  
|<span data-ttu-id="42e38-124">文本对比度级别</span><span class="sxs-lookup"><span data-stu-id="42e38-124">Text contrast level</span></span>|<span data-ttu-id="42e38-125">描述显示文本的对比度级别。</span><span class="sxs-lookup"><span data-stu-id="42e38-125">Describes the level of contrast for displayed text.</span></span>|  
  
 <span data-ttu-id="42e38-126">这些设置可由知道如何引用已识别[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType 注册表设置的外部配置实用程序来访问。</span><span class="sxs-lookup"><span data-stu-id="42e38-126">These settings can be accessed by an external configuration utility that knows how to reference the identified [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType registry settings.</span></span> <span data-ttu-id="42e38-127">还可以直接使用 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 注册表编辑器来访问这些值，从而创建或修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="42e38-127">These settings can also be created or modified by accessing the values directly by using the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Registry Editor.</span></span>  
  
 <span data-ttu-id="42e38-128">如果未设置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ClearType 注册表设置 (这是默认状态), 则应用程序将查询系统参数信息以实现字体平滑设置。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e38-128">If the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType registry settings are not set (which is the default state), the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application queries the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] system parameters information for font smoothing settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42e38-129">有关枚举显示设备名称的信息, 请参阅`SystemParametersInfo` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]函数。</span><span class="sxs-lookup"><span data-stu-id="42e38-129">For information on enumerating display device names, see the `SystemParametersInfo`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function.</span></span>  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a><span data-ttu-id="42e38-130">ClearType 级别</span><span class="sxs-lookup"><span data-stu-id="42e38-130">ClearType Level</span></span>  
 <span data-ttu-id="42e38-131">ClearType 级别允许你根据颜色敏感度和个人认知度调整文本的呈现。</span><span class="sxs-lookup"><span data-stu-id="42e38-131">The ClearType level allows you to adjust the rendering of text based on the color sensitivity and perception of an individual.</span></span> <span data-ttu-id="42e38-132">对于某些人而言, 在其最高级别使用 ClearType 的文本呈现不会产生最佳阅读体验。</span><span class="sxs-lookup"><span data-stu-id="42e38-132">For some individuals, the rendering of text that uses ClearType at its highest level does not produce the best reading experience.</span></span>  
  
 <span data-ttu-id="42e38-133">ClearType 级别为介于0到100之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="42e38-133">The ClearType level is an integer value that ranges from 0 to 100.</span></span> <span data-ttu-id="42e38-134">默认级别为 100, 这意味着 ClearType 使用显示设备的色带元素的最大容量。</span><span class="sxs-lookup"><span data-stu-id="42e38-134">The default level is 100, which means ClearType uses the maximum capability of the color stripe elements of the display device.</span></span> <span data-ttu-id="42e38-135">但 ClearType 级别0将文本呈现为灰色刻度。</span><span class="sxs-lookup"><span data-stu-id="42e38-135">However, a ClearType level of 0 renders text as gray scale.</span></span> <span data-ttu-id="42e38-136">通过将 ClearType 级别设置为介于0到100之间的某个位置, 可以创建适合个人颜色敏感度的中间级别。</span><span class="sxs-lookup"><span data-stu-id="42e38-136">By setting the ClearType level somewhere between 0 and 100, you can create an intermediate level that is suitable to an individual's color sensitivity.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="42e38-137">注册表设置</span><span class="sxs-lookup"><span data-stu-id="42e38-137">Registry Setting</span></span>  
 <span data-ttu-id="42e38-138">ClearType 级别的注册表设置位置是对应于特定显示设备名称的单个用户设置:</span><span class="sxs-lookup"><span data-stu-id="42e38-138">The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="42e38-139">对于用户的每个显示设备名称, 会`ClearTypeLevel`定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="42e38-139">For each display device name for a user, a `ClearTypeLevel` DWORD value is defined.</span></span> <span data-ttu-id="42e38-140">以下屏幕截图显示 ClearType 级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="42e38-140">The following screenshot shows the Registry Editor setting for the ClearType level.</span></span>  
  
 ![注册表编辑器中的 ClearType 设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="42e38-142">应用程序以两种模式之一呈现文本, 但不带 ClearType。</span><span class="sxs-lookup"><span data-stu-id="42e38-142">applications render text in one of either two modes, with and without ClearType.</span></span> <span data-ttu-id="42e38-143">如果呈现的文本没有 ClearType, 则称为灰度呈现。</span><span class="sxs-lookup"><span data-stu-id="42e38-143">When text is rendered without ClearType, it is referred to as gray scale rendering.</span></span>  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a><span data-ttu-id="42e38-144">伽马级别</span><span class="sxs-lookup"><span data-stu-id="42e38-144">Gamma Level</span></span>  
 <span data-ttu-id="42e38-145">伽玛级别指的是像素值和亮度之间的非线性关系。</span><span class="sxs-lookup"><span data-stu-id="42e38-145">The gamma level refers to the nonlinear relationship between a pixel value and luminance.</span></span> <span data-ttu-id="42e38-146">伽玛级别设置应对应于显示设备的物理特性；否则呈现的输出中可能会出现失真。</span><span class="sxs-lookup"><span data-stu-id="42e38-146">The gamma level setting should correspond to the physical characteristics of the display device; otherwise, distortions in rendered output may occur.</span></span> <span data-ttu-id="42e38-147">例如，测试可能显得太宽或太窄，或者字形的垂直主体的边缘上可能会出现彩色条纹。</span><span class="sxs-lookup"><span data-stu-id="42e38-147">For example, test may appear too wide or too narrow, or color fringes may appear on the edges of vertical stems of glyphs.</span></span>  
  
 <span data-ttu-id="42e38-148">伽马级别是一个介于 1000 到 2200 之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="42e38-148">The gamma level is an integer value that ranges from 1000 to 2200.</span></span> <span data-ttu-id="42e38-149">默认级别为 1900。</span><span class="sxs-lookup"><span data-stu-id="42e38-149">The default level is 1900.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="42e38-150">注册表设置</span><span class="sxs-lookup"><span data-stu-id="42e38-150">Registry Setting</span></span>  
 <span data-ttu-id="42e38-151">伽马级别的注册表设置位置是对应于特定显示设备名称的本地计算机设置：</span><span class="sxs-lookup"><span data-stu-id="42e38-151">The registry setting location for the gamma level is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="42e38-152">对于用户的每个显示设备名称, 会`GammaLevel`定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="42e38-152">For each display device name for a user, a `GammaLevel` DWORD value is defined.</span></span> <span data-ttu-id="42e38-153">以下屏幕快照显示了伽马级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="42e38-153">The following screenshot shows the Registry Editor setting for the gamma level.</span></span>  
  
 ![注册表编辑器中的 ClearType 伽玛级别设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a><span data-ttu-id="42e38-155">像素结构</span><span class="sxs-lookup"><span data-stu-id="42e38-155">Pixel Structure</span></span>  
 <span data-ttu-id="42e38-156">像素结构描述构成显示设备的像素的类型。</span><span class="sxs-lookup"><span data-stu-id="42e38-156">The pixel structure describes the type of pixels that make up a display device.</span></span> <span data-ttu-id="42e38-157">像素结构定义为三种类型之一：</span><span class="sxs-lookup"><span data-stu-id="42e38-157">The pixel structure is defined as one of three types:</span></span>  
  
|<span data-ttu-id="42e38-158">类型</span><span class="sxs-lookup"><span data-stu-id="42e38-158">Type</span></span>|<span data-ttu-id="42e38-159">值</span><span class="sxs-lookup"><span data-stu-id="42e38-159">Value</span></span>|<span data-ttu-id="42e38-160">描述</span><span class="sxs-lookup"><span data-stu-id="42e38-160">Description</span></span>|  
|----------|-----------|-----------------|  
|<span data-ttu-id="42e38-161">平面</span><span class="sxs-lookup"><span data-stu-id="42e38-161">Flat</span></span>|<span data-ttu-id="42e38-162">0</span><span class="sxs-lookup"><span data-stu-id="42e38-162">0</span></span>|<span data-ttu-id="42e38-163">显示设备没有像素结构。</span><span class="sxs-lookup"><span data-stu-id="42e38-163">The display device has no pixel structure.</span></span> <span data-ttu-id="42e38-164">这意味着每种颜色的光源均匀分布在像素区域上，称为灰度呈现。</span><span class="sxs-lookup"><span data-stu-id="42e38-164">This means that light sources for each color are spread equally on the pixel area—this is referred to as gray scale rendering.</span></span> <span data-ttu-id="42e38-165">这是标准显示设备的工作方式。</span><span class="sxs-lookup"><span data-stu-id="42e38-165">This is how a standard display device works.</span></span> <span data-ttu-id="42e38-166">ClearType 从不应用于呈现的文本。</span><span class="sxs-lookup"><span data-stu-id="42e38-166">ClearType is never applied to the rendered text.</span></span>|  
|<span data-ttu-id="42e38-167">RGB</span><span class="sxs-lookup"><span data-stu-id="42e38-167">RGB</span></span>|<span data-ttu-id="42e38-168">1</span><span class="sxs-lookup"><span data-stu-id="42e38-168">1</span></span>|<span data-ttu-id="42e38-169">显示设备的像素由三种色条按以下顺序构成：红色、绿色和蓝色。</span><span class="sxs-lookup"><span data-stu-id="42e38-169">The display device has pixels that consist of three stripes in the following order: red, green, and blue.</span></span> <span data-ttu-id="42e38-170">ClearType 应用于呈现的文本。</span><span class="sxs-lookup"><span data-stu-id="42e38-170">ClearType is applied to the rendered text.</span></span>|  
|<span data-ttu-id="42e38-171">BGR</span><span class="sxs-lookup"><span data-stu-id="42e38-171">BGR</span></span>|<span data-ttu-id="42e38-172">2</span><span class="sxs-lookup"><span data-stu-id="42e38-172">2</span></span>|<span data-ttu-id="42e38-173">显示设备的像素由三种色条按以下顺序构成：蓝色、绿色和红色。</span><span class="sxs-lookup"><span data-stu-id="42e38-173">The display device has pixels that consist of three stripes in the following order: blue, green, and red.</span></span> <span data-ttu-id="42e38-174">ClearType 应用于呈现的文本。</span><span class="sxs-lookup"><span data-stu-id="42e38-174">ClearType is applied to the rendered text.</span></span> <span data-ttu-id="42e38-175">注意该顺序与 RGB 类型相反。</span><span class="sxs-lookup"><span data-stu-id="42e38-175">Notice how the order is inverted from the RGB type.</span></span>|  
  
 <span data-ttu-id="42e38-176">像素结构对应于 0 到 2 之间的一个整数值。</span><span class="sxs-lookup"><span data-stu-id="42e38-176">The pixel structure corresponds to an integer value that ranges from 0 to 2.</span></span> <span data-ttu-id="42e38-177">默认级别为 0，表示平面像素结构。</span><span class="sxs-lookup"><span data-stu-id="42e38-177">The default level is 0, which represents a flat pixel structure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42e38-178">有关枚举显示设备名称的信息, 请参阅`EnumDisplayDevices` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]函数。</span><span class="sxs-lookup"><span data-stu-id="42e38-178">For information on enumerating display device names, see the `EnumDisplayDevices`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="42e38-179">注册表设置</span><span class="sxs-lookup"><span data-stu-id="42e38-179">Registry Setting</span></span>  
 <span data-ttu-id="42e38-180">像素结构的注册表设置位置是对应于特定显示设备名称的本地计算机设置：</span><span class="sxs-lookup"><span data-stu-id="42e38-180">The registry setting location for the pixel structure is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="42e38-181">对于用户的每个显示设备名称, 会`PixelStructure`定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="42e38-181">For each display device name for a user, a `PixelStructure` DWORD value is defined.</span></span> <span data-ttu-id="42e38-182">以下屏幕快照显示了像素结构的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="42e38-182">The following screenshot shows the Registry Editor setting for the pixel structure.</span></span>  
  
 ![注册表编辑器中的 ClearType 伽玛级别设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a><span data-ttu-id="42e38-184">文本对比度级别</span><span class="sxs-lookup"><span data-stu-id="42e38-184">Text Contrast Level</span></span>  
 <span data-ttu-id="42e38-185">通过文本对比度级别可以根据字形的主体宽度来调整文本的呈现。</span><span class="sxs-lookup"><span data-stu-id="42e38-185">The text contrast level allows you to adjust the rendering of text based on the stem widths of glyphs.</span></span> <span data-ttu-id="42e38-186">文本对比度级别是一个 0 到 6 之间的整数值 - 整数值越大，主体就越宽。</span><span class="sxs-lookup"><span data-stu-id="42e38-186">The text contrast level is an integer value that ranges from 0 to 6—the larger the integer value, the wider the stem.</span></span> <span data-ttu-id="42e38-187">默认级别为 1。</span><span class="sxs-lookup"><span data-stu-id="42e38-187">The default level is 1.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="42e38-188">注册表设置</span><span class="sxs-lookup"><span data-stu-id="42e38-188">Registry Setting</span></span>  
 <span data-ttu-id="42e38-189">文本对比度级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：</span><span class="sxs-lookup"><span data-stu-id="42e38-189">The registry setting location for the text contrast level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="42e38-190">对于用户的每个显示设备名称, 会`TextContrastLevel`定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="42e38-190">For each display device name for a user, a `TextContrastLevel` DWORD value is defined.</span></span> <span data-ttu-id="42e38-191">以下屏幕快照显示了文本对比度级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="42e38-191">The following screenshot shows the Registry Editor setting for the text contrast level.</span></span>  
  
 ![注册表编辑器中的 ClearType 设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a><span data-ttu-id="42e38-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="42e38-193">See also</span></span>

- [<span data-ttu-id="42e38-194">ClearType 概述</span><span class="sxs-lookup"><span data-stu-id="42e38-194">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="42e38-195">ClearType 抗锯齿</span><span class="sxs-lookup"><span data-stu-id="42e38-195">ClearType Antialiasing</span></span>](/windows/desktop/gdi/cleartype-antialiasing)
