---
title: 不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: a209a83ce5bd3ecd9580abab330f1e09ecc3864e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61594836"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese
应用程序尝试组合 `VbStrConv` 枚举成员 `SimplifiedChinese` 和 `TraditionalChinese`，而它们是互斥的。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 删除 `VbStrConv.SimplifiedChinese` 或 `VbStrConv.TraditionalChinese`。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Globalization>

- [基于 .NET Framework 的国际应用程序简介](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
