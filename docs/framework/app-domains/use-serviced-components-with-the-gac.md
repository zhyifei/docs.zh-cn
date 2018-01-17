---
title: "在服务组件中使用全局程序集缓存"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb9bd85797dd129f6f34992c58c9772668ce2cb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a>在服务组件中使用全局程序集缓存
服务组件（托管代码 COM+ 组件）应置于全局程序集缓存中。 在有些方案中，公共语言运行时和 COM+ 服务能够处理不在全局程序集缓存中的服务组件，而在有些方案中则不能。 以下方案对此进行了说明：  
  
-   对于 COM+ 服务器应用程序中的服务组件，包含组件的程序集必须位于全局程序集缓存中，因为 Dllhost.exe 不在包含服务组件的目录中运行。  
  
-   对于 COM+ 库应用程序中的服务组件，运行时和 COM+ 服务可通过搜索当前目录来解析对包含组件的程序集的引用。 在这种情况下，程序集不需要位于全局程序集缓存中。  
  
-   对于 ASP.NET 应用程序中的服务组件，情况则有所不同。 如果将包含服务组件的程序集放在应用程序基的 bin 目录中，并使用按需注册，程序集将被卷影复制到下载缓存，因为 ASP.NET 需利用运行时的卷影功能。  
  
## <a name="see-also"></a>请参阅  
 [使用程序集和全局程序集缓存](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
