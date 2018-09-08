---
title: 替换 Principal 对象
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfcd912fc16aa8d4b89a4f455d65b0294593cead
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205849"
---
# <a name="replacing-a-principal-object"></a>替换 Principal 对象
提供身份验证服务的应用程序必须能够为给定的线程替换 **主体** 对象 (<xref:System.Security.Principal.IPrincipal>)。 此外，安全系统必须帮助保护这种替换 **主体** 对象的能力，因为恶意附加的不正确的 **主体** 会通过声明一个不真实的身份或角色危及应用程序的安全。 因此，应用程序，需要能够替换**主体**必须授予对象<xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>对象以进行主体控制。 （请注意，对于执行基于角色的安全检查或创建 **主体** 对象，此权限不是必需的。）  
  
 可通过执行以下任务替换当前 **主体** 对象：  
  
1.  创建替换的 **主体** 对象和关联的 **标识** 对象。  
  
2.  将新的 **主体** 附加到调用上下文。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建一般主体对象并用该对象来设置线程的主体。  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
- [主体和标识对象](../../../docs/standard/security/principal-and-identity-objects.md)
