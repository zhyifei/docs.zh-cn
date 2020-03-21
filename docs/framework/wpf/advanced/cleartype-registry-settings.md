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
# <a name="cleartype-registry-settings"></a>ClearType 注册表设置
本主题概述了 WPF 应用程序使用的 Microsoft ClearType 注册表设置。  

<a name="overview"></a>
## <a name="technology-overview"></a>技术概述  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]向显示设备呈现文本的应用程序使用 ClearType 功能提供增强的阅读体验。 ClearType 是 Microsoft 开发的一种软件技术，可提高现有 LCD（液晶显示器）文本的可读性，例如笔记本电脑屏幕、袖珍 PC 屏幕和平板显示器。 ClearType 的工作原理是访问 LCD 屏幕每个像素中的单个垂直颜色条纹元素。 有关清除类型的详细信息，请参阅[清除类型概述](cleartype-overview.md)。  
  
 在各种显示设备上查看时，使用 ClearType 呈现的文本可能会明显不同。 例如，少量监视器以蓝色、绿色、红色顺序实现颜色条纹元素，而不是更常见的红色、绿色、蓝色 （RGB） 顺序。  
  
 当具有不同颜色敏感度级别的个人查看时，使用 ClearType 呈现的文本也会出现显著差异。 某些人能够比别人更擅长发觉颜色的微小差异。  
  
 在每种情况下，都需要修改 ClearType 功能，以便为每个人提供最佳的阅读体验。  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>注册表设置  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]指定用于控制 ClearType 功能的四个注册表设置：  
  
|设置|说明|  
|-------------|-----------------|  
|清除类型级别|描述清晰类型颜色清晰度级别。|  
|伽马级别|描述显示设备的像素颜色组件的级别。|  
|像素结构|描述显示设备的像素排列。|  
|文本对比度级别|描述显示文本的对比度级别。|  
  
 这些设置可以通过外部配置实用程序访问，该实用程序知道如何引用已识别[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的 ClearType 注册表设置。 还可以通过使用 Windows 注册表编辑器直接访问这些值来创建或修改这些设置。  
  
 如果未设置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType 注册表设置（这是默认状态），[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序将查询 Windows 系统参数信息以进行字体平滑设置。  
  
> [!NOTE]
> 有关枚举显示设备名称的信息，请参阅`SystemParametersInfo`Win32 函数。  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a>ClearType 级别  
 ClearType 级别允许您根据个人的颜色敏感度和感知来调整文本的呈现。 对于某些个人，在最高级别使用 ClearType 的文本的呈现不会产生最佳的阅读体验。  
  
 ClearType 级别是一个介于 0 到 100 的整数值。 默认级别为 100，这意味着 ClearType 使用显示设备的颜色条带元素的最大功能。 但是，ClearType 级别为 0 会将文本渲染为灰色比例。 通过将 ClearType 级别设置为介于 0 和 100 之间，可以创建适合个人颜色敏感度的中间级别。  
  
### <a name="registry-setting"></a>注册表设置  
 ClearType 级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称，将定义一`ClearTypeLevel`个 DWORD 值。 以下屏幕截图显示了 ClearType 级别的注册表编辑器设置。  
  
 ![清除注册表编辑器中的设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序以两种模式之一呈现文本，带和没有 ClearType。 在未显示 ClearType 的情况下呈现文本时，它称为灰度渲染。  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a>伽马级别  
 伽玛级别指的是像素值和亮度之间的非线性关系。 伽玛级别设置应对应于显示设备的物理特性；否则呈现的输出中可能会出现失真。 例如，文本可能显得过于宽或太窄，或者颜色条纹可能出现在字形垂直茎的边缘。  
  
 伽马级别是一个介于 1000 到 2200 之间的整数值。 默认级别为 1900。  
  
### <a name="registry-setting"></a>注册表设置  
 伽马级别的注册表设置位置是对应于特定显示设备名称的本地计算机设置：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称，将定义一`GammaLevel`个 DWORD 值。 以下屏幕快照显示了伽马级别的注册表编辑器设置。  
  
 ![清除注册表编辑器中的伽马级设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a>像素结构  
 像素结构描述构成显示设备的像素的类型。 像素结构定义为三种类型之一：  
  
|类型|值|说明|  
|----------|-----------|-----------------|  
|平面|0|显示设备没有像素结构。 这意味着每种颜色的光源均匀分布在像素区域上，称为灰度呈现。 这是标准显示设备的工作方式。 ClearType 永远不会应用于渲染的文本。|  
|RGB|1|显示设备的像素由三种色条按以下顺序构成：红色、绿色和蓝色。 清除类型应用于渲染的文本。|  
|BGR|2|显示设备的像素由三种色条按以下顺序构成：蓝色、绿色和红色。 清除类型应用于渲染的文本。 注意该顺序与 RGB 类型相反。|  
  
 像素结构对应于 0 到 2 之间的一个整数值。 默认级别为 0，表示平面像素结构。  
  
> [!NOTE]
> 有关枚举显示设备名称的信息，请参阅`EnumDisplayDevices`Win32 函数。  
  
### <a name="registry-setting"></a>注册表设置  
 像素结构的注册表设置位置是对应于特定显示设备名称的本地计算机设置：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称，将定义一`PixelStructure`个 DWORD 值。 以下屏幕快照显示了像素结构的注册表编辑器设置。  
  
 ![清除注册表编辑器中的伽马级设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a>文本对比度级别  
 通过文本对比度级别可以根据字形的主体宽度来调整文本的呈现。 文本对比度级别是一个 0 到 6 之间的整数值 - 整数值越大，主体就越宽。 默认级别为 1。  
  
### <a name="registry-setting"></a>注册表设置  
 文本对比度级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称，将定义一`TextContrastLevel`个 DWORD 值。 以下屏幕快照显示了文本对比度级别的注册表编辑器设置。  
  
 ![清除注册表编辑器中的设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>另请参阅

- [ClearType 概述](cleartype-overview.md)
- [ClearType 抗锯齿](/windows/desktop/gdi/cleartype-antialiasing)
