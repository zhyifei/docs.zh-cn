---
title: 不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: b3c75e64624d6be6df2db216a0ad336c9ef583a7
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197222"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese
应用程序尝试组合 `VbStrConv` 枚举成员 `SimplifiedChinese` 和 `TraditionalChinese`，而它们是互斥的。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 删除 `VbStrConv.SimplifiedChinese` 或 `VbStrConv.TraditionalChinese`。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Globalization>

- [开发全球化和本地化应用](/visualstudio/ide/globalizing-and-localizing-applications)
