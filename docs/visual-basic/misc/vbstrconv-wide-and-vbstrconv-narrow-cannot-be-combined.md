---
title: "不能组合 VbStrConv.Wide 和 VbStrConv.Narrow"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb42ffd72a7e1f9bceabc8e8b67310b4ca2ab716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>不能组合 VbStrConv.Wide 和 VbStrConv.Narrow
你的应用程序尝试组合 `VbStrConv` 枚举成员 `Wide` 和 `Narrow`，而它们是互斥的。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  删除 `VbStrConv.Wide` 或 `VbStrConv.Narrow`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Globalization>  
 [NOTINBUILD VbStrConv 枚举](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)  
 [基于 .NET Framework 的国际应用程序简介](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
