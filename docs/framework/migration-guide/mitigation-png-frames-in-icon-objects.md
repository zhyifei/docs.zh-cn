---
title: "缓解：图标对象中的 PNG 帧 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9d5088d70397e21cb555c78b2701960ee69bde66
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-png-frames-in-icon-objects"></a>缓解：图标对象中的 PNG 帧
自 .NET Framework 4.6 起，<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 方法可将带有 PNG 帧的图标成功转换成 <xref:System.Drawing.Bitmap> 对象。  
  
 在面向 .NET Framework 4.5.2 及更早版本的应用中，如果 <xref:System.Drawing.Icon> 对象具有 PNG 帧，<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 方法会引发 <xref:System.ArgumentOutOfRangeException> 异常。  
  
## <a name="impact"></a>影响  
 此更改会影响重新编译为定位 .NET Framework 4.6 且对在 <xref:System.Drawing.Icon> 对象包含 PNG 帧时抛出的 <xref:System.ArgumentOutOfRangeException> 实现特殊处理的应用程序。 在 .NET Framework 4.6 控制下运行时，可以成功转换，且不再抛出 <xref:System.ArgumentOutOfRangeException>，因此不再需要调用异常处理程序。  
  
### <a name="mitigation"></a>缓解操作  
 如果不需要此行为，可以在 app.config 文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的元素，从而保留旧行为：  
  
```  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
  
```  
  
 如果 app.config 文件中已包含 `AppContextSwitchOverrides` 元素，新值应与 `value` 特性合并，如下所示：  
  
```  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
