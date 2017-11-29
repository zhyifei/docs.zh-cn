---
title: "ClearType 注册表设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc4411c8141579150cde1bda2e46d7d2abe42e9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cleartype-registry-settings"></a>ClearType 注册表设置
本主题提供的概述[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]所使用的注册表设置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。  
  
  
<a name="overview"></a>   
## <a name="technology-overview"></a>技术概述  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序呈现文本的显示设备使用[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]功能以提供增强的阅读体验。 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 是一种由 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 开发的软件技术，可提高现有 LCD（液晶显示器，如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器）上文本的可读性。 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 在工作时访问 LCD 屏幕中每个像素的各个垂直色条元素。 有关详细信息[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]，请参阅[ClearType 概述](../../../../docs/framework/wpf/advanced/cleartype-overview.md)。  
  
 呈现所使用的文本[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]可以出现在不同的显示设备上查看时明显不同。 例如，监视器的少量实现蓝色、 绿色、 红色顺序中的颜色条带元素而不是更常见的红色、 绿色、 蓝色 ( [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) 顺序。  
  
 呈现所使用的文本[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]，也会出现明显不同查看由具有不同的颜色敏感度级别时。 某些人能够比别人更擅长发觉颜色的微小差异。  
  
 在每个这些情况下，[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]功能需要进行修改以提供最佳的每个人阅读体验。  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>注册表设置  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]指定四个注册表设置控制[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]功能：  
  
|设置|描述|  
|-------------|-----------------|  
|[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 级别|描述的级别[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]色彩清晰度。|  
|伽马级别|描述显示设备的像素颜色组件的级别。|  
|像素结构|描述显示设备的像素排列。|  
|文本对比度级别|描述显示文本的对比度级别。|  
  
 这些设置，可以访问由知道如何引用标识外部配置实用工具[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]注册表设置。 还可以直接使用 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 注册表编辑器来访问这些值，从而创建或修改这些设置。  
  
 如果[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]注册表设置未设置 （这是默认状态），[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序查询[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]系统字体平滑显示设置的参数信息。  
  
> [!NOTE]
>  有关枚举显示设备名称的信息，请参阅`SystemParametersInfo`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]函数。  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a>ClearType 级别  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]级别允许你调整颜色敏感度和感知的单个基于文本的呈现。 对于某些人的文本呈现，它使用[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]在其最高级别不会产生最佳的阅读体验。  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]级别是范围从 0 到 100 的整数值。 默认级别为 100，这意味着[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]使用颜色条带元素的显示设备的最大能力。 但是，[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]级别为 0 将呈现为灰度状态文本。 通过设置[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]介于 0 和 100 级别，你可以创建适用于个人的颜色敏感度中间级别。  
  
### <a name="registry-setting"></a>注册表设置  
 注册表设置位置[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]级别是对应于特定显示设备名称的单个用户设置：  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户，每个显示设备名称`ClearTypeLevel`定义 DWORD 值。 以下屏幕截图显示的注册表编辑器设置[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]级别。  
  
 ![注册表编辑器中的 ClearType 设置](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序呈现文本中使用和不使用任一两种模式之一[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]。 情况下呈现文本时[!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]，它称为灰度呈现。  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a>伽马级别  
 伽玛级别指的是像素值和亮度之间的非线性关系。 伽玛级别设置应对应于显示设备的物理特性；否则呈现的输出中可能会出现失真。 例如，测试可能显得太宽或太窄，或者字形的垂直主体的边缘上可能会出现彩色条纹。  
  
 伽马级别是一个介于 1000 到 2200 之间的整数值。 默认级别为 1900。  
  
### <a name="registry-setting"></a>注册表设置  
 伽马级别的注册表设置位置是对应于特定显示设备名称的本地计算机设置：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户，每个显示设备名称`GammaLevel`定义 DWORD 值。 以下屏幕快照显示了伽马级别的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 设置](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a>像素结构  
 像素结构描述构成显示设备的像素的类型。 像素结构定义为三种类型之一：  
  
|类型|值|说明|  
|----------|-----------|-----------------|  
|平面|0|显示设备没有像素结构。 这意味着每种颜色的光源均匀分布在像素区域上，称为灰度呈现。 这是标准显示设备的工作方式。 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 从不应用于呈现的文本。|  
|RGB|1|显示设备的像素由三种色条按以下顺序构成：红色、绿色和蓝色。 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 应用于呈现的文本。|  
|BGR|2|显示设备的像素由三种色条按以下顺序构成：蓝色、绿色和红色。 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 应用于呈现的文本。 注意该顺序与 RGB 类型相反。|  
  
 像素结构对应于 0 到 2 之间的一个整数值。 默认级别为 0，表示平面像素结构。  
  
> [!NOTE]
>  有关枚举显示设备名称的信息，请参阅`EnumDisplayDevices`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]函数。  
  
### <a name="registry-setting"></a>注册表设置  
 像素结构的注册表设置位置是对应于特定显示设备名称的本地计算机设置：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户，每个显示设备名称`PixelStructure`定义 DWORD 值。 以下屏幕快照显示了像素结构的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 设置](../../../../docs/framework/wpf/advanced/media/cleartyperegistry02.png "ClearTypeRegistry02")  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a>文本对比度级别  
 通过文本对比度级别可以根据字形的主体宽度来调整文本的呈现。 文本对比度级别是一个 0 到 6 之间的整数值 - 整数值越大，主体就越宽。 默认级别为 1。  
  
### <a name="registry-setting"></a>注册表设置  
 文本对比度级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户，每个显示设备名称`TextContrastLevel`定义 DWORD 值。 以下屏幕快照显示了文本对比度级别的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 设置](../../../../docs/framework/wpf/advanced/media/cleartyperegistry01.png "ClearTypeRegistry01")  
  
## <a name="see-also"></a>另请参阅  
 [ClearType 概述](../../../../docs/framework/wpf/advanced/cleartype-overview.md)  
 [ClearType 抗锯齿](https://msdn.microsoft.com/library/dd183433(v=vs.85).aspx)
