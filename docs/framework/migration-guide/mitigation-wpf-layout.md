---
title: "缓解：WPF 布局"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1dcbe970281f3d9cf3b8ffe9adb543afc120ae6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="e14fd-102">缓解：WPF 布局</span><span class="sxs-lookup"><span data-stu-id="e14fd-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="e14fd-103">WPF 控件的布局可能稍有变化。</span><span class="sxs-lookup"><span data-stu-id="e14fd-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e14fd-104">影响</span><span class="sxs-lookup"><span data-stu-id="e14fd-104">Impact</span></span>  
 <span data-ttu-id="e14fd-105">此更改的结果是：</span><span class="sxs-lookup"><span data-stu-id="e14fd-105">As a result of this change:</span></span>  
  
-   <span data-ttu-id="e14fd-106">元素的宽度或高度最多可以扩大或收缩一个像素。</span><span class="sxs-lookup"><span data-stu-id="e14fd-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
-   <span data-ttu-id="e14fd-107">对象的位置最多可以移动一个像素。</span><span class="sxs-lookup"><span data-stu-id="e14fd-107">The placement of an object can move by at most one pixel.</span></span>  
  
-   <span data-ttu-id="e14fd-108">居中的元素最多可以垂直或水平地偏离中心一个像素。</span><span class="sxs-lookup"><span data-stu-id="e14fd-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="e14fd-109">默认情况下，仅对面向 .NET Framework 4.6 的应用启用此新布局。</span><span class="sxs-lookup"><span data-stu-id="e14fd-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e14fd-110">缓解</span><span class="sxs-lookup"><span data-stu-id="e14fd-110">Mitigation</span></span>  
 <span data-ttu-id="e14fd-111">由于这种修改往往会消除高 DPI 处 WPF 控件的右侧或底部剪辑，因此面向早期版本的 .NET framework 但在.NET Framework 4.6 上运行的应用可以通过将下面的行添加到 app.config 文件的 `<runtime>` 部分来选择加入此新行为：</span><span class="sxs-lookup"><span data-stu-id="e14fd-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="e14fd-112">面向 .NET Framework 4.6 但希望 WPF 控件使用之前的布局算法来呈现的应用可以通过将下面的行添加到 app.config 文件的 `<runtime>` 部分来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="e14fd-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="e14fd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e14fd-113">See Also</span></span>  
 [<span data-ttu-id="e14fd-114">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="e14fd-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
