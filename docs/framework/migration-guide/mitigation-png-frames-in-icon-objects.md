---
title: 缓解：图标对象中的 PNG 帧
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: 1a4ae0c069a4cd6d53bce77e64822ebf3fbb5361
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457878"
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="54e8b-102">缓解：图标对象中的 PNG 帧</span><span class="sxs-lookup"><span data-stu-id="54e8b-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="54e8b-103">从 .NET Framework 4.6 开始， <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 方法成功将带 PNG 帧的图标转换为 <xref:System.Drawing.Bitmap> 对象。</span><span class="sxs-lookup"><span data-stu-id="54e8b-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="54e8b-104">在面向 .NET Framework 4.5.2 和更早版本的应用中， <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 方法在 <xref:System.ArgumentOutOfRangeException> 对象具有 PNG 帧时引发 <xref:System.Drawing.Icon> 异常。</span><span class="sxs-lookup"><span data-stu-id="54e8b-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="54e8b-105">影响</span><span class="sxs-lookup"><span data-stu-id="54e8b-105">Impact</span></span>  
 <span data-ttu-id="54e8b-106">此更改会影响以下应用：重新编译为面向 .NET Framework 4.6 的应用，以及对在 <xref:System.ArgumentOutOfRangeException> 对象具有 PNG 帧时引发的 <xref:System.Drawing.Icon> 实施特殊处理的应用。</span><span class="sxs-lookup"><span data-stu-id="54e8b-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="54e8b-107">在.NET Framework 4.6 下运行时，转换成功，不再引发 <xref:System.ArgumentOutOfRangeException> ，因此不再调用异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="54e8b-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="54e8b-108">缓解</span><span class="sxs-lookup"><span data-stu-id="54e8b-108">Mitigation</span></span>  
 <span data-ttu-id="54e8b-109">如果不需要此行为，可以在 app.config 文件的 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的元素，从而保留旧行为：</span><span class="sxs-lookup"><span data-stu-id="54e8b-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="54e8b-110">如果 app.config 文件中已包含 `AppContextSwitchOverrides` 元素，新值应与 `value` 特性合并，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54e8b-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="54e8b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="54e8b-111">See also</span></span>

- [<span data-ttu-id="54e8b-112">应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="54e8b-112">Application compatibility</span></span>](application-compatibility.md)
