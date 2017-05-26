---
title: ".NET Framework 4.6 中的应用程序兼容性 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility, .NET Framework
- application compatibility. NET Framework 4.6
ms.assetid: 7a3fd352-a8ba-4f9a-8250-951f2c994248
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 32bbbf7cb9acd71f5b8e28b7b12aab706221fab9
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-46"></a>.NET Framework 4.6 中的应用程序兼容性
本主题提供指向有关 NET Framework 4.5.2 与 4.6 之间的应用程序兼容性问题的信息的链接。 此问题分为两个类别：  
  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)  
 运行时更改影响所有在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 下运行和使用特定功能的应用。  
  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)  
 重定目标更改会影响重新编译以面向 .NET Framework 4.5、4.5.1、4.5.2 或 4.6 的应用。 它们包括：  
  
-   设计时环境的更改。 例如，生成工具可能在之前没有发出警告时发出警告。  
  
-   运行时环境的更改。 它们仅影响专门面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的应用。 面向之前版本 .NET Framework 的应用的行为与在这些版本下运行时相同。  
  
 在介绍运行时更改和重定目标更改的主题中，我们已根据其预期影响为单个项目进行了分类，如下所示：  
  
 主要  
 这是显著的更改，可影响大量应用或需要修改大量代码。  
  
 次要  
 此更改影响少量应用或需要修改少量代码。  
  
 边缘情况  
 此类更改仅在少数非常特定的情况下影响应用。  
  
 透明  
 此类更改对应用的开发人员或用户没有明显影响。 不需要由于此更改而修改应用。  
  
## <a name="see-also"></a>另请参阅  
 [版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [4.5.2 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
