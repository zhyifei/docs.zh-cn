---
title: 不能组合 VbStrConv.Wide 和 VbStrConv.Narrow
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 917fcdfcb34778074db6a19c04e12c3cf8de90dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61818750"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>不能组合 VbStrConv.Wide 和 VbStrConv.Narrow
你的应用程序尝试组合 `VbStrConv` 枚举成员 `Wide` 和 `Narrow`，而它们是互斥的。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 删除 `VbStrConv.Wide` 或 `VbStrConv.Narrow`。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Globalization>

- [基于 .NET Framework 的国际应用程序简介](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
