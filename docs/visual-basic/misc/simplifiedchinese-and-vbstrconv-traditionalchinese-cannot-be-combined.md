---
title: "不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 602f375eece2d79eb2f839b220b7774ebc3a847e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese
应用程序尝试组合 `VbStrConv` 枚举成员 `SimplifiedChinese` 和 `TraditionalChinese`，而它们是互斥的。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除 `VbStrConv.SimplifiedChinese` 或 `VbStrConv.TraditionalChinese`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Globalization>  
 [NOTINBUILD VbStrConv 枚举](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)  
 [基于 .NET Framework 的国际应用程序简介](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
