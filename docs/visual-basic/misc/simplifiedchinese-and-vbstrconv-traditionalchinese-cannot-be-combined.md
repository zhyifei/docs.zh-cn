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
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="21829-102">不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese</span><span class="sxs-lookup"><span data-stu-id="21829-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="21829-103">应用程序尝试组合 `VbStrConv` 枚举成员 `SimplifiedChinese` 和 `TraditionalChinese`，而它们是互斥的。</span><span class="sxs-lookup"><span data-stu-id="21829-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="21829-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="21829-104">To correct this error</span></span>  
  
- <span data-ttu-id="21829-105">删除 `VbStrConv.SimplifiedChinese` 或 `VbStrConv.TraditionalChinese`。</span><span class="sxs-lookup"><span data-stu-id="21829-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21829-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="21829-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="21829-107">开发全球化和本地化应用</span><span class="sxs-lookup"><span data-stu-id="21829-107">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
