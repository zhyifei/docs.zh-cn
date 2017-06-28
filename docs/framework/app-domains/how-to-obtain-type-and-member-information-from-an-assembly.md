---
title: "如何：从程序集获取类型和成员信息 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 42a950493d6042581d98d3be3f4787df9752af16
ms.contentlocale: zh-cn
ms.lasthandoff: 06/02/2017

---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a>如何：从程序集获得类型和成员信息
<xref:System.Reflection> 命名空间包含许多从程序集中获取信息的方法。 本部分介绍其中的一种方法。 有关其他信息，请参阅[反射概述](../../../docs/framework/reflection-and-codedom/reflection.md)。  
  
 下例演示从程序集获取类型和成员信息。  
  
## <a name="example"></a>示例  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)] [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)][!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a>另请参阅  
 [对应用程序域进行编程](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [反射](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [使用应用程序域](../../../docs/framework/app-domains/use.md)
