---
title: 不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: a209a83ce5bd3ecd9580abab330f1e09ecc3864e
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58043281"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="5a75c-102">不能组合 SimplifiedChinese 和 VbStrConv.TraditionalChinese</span><span class="sxs-lookup"><span data-stu-id="5a75c-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="5a75c-103">应用程序尝试组合 `VbStrConv` 枚举成员 `SimplifiedChinese` 和 `TraditionalChinese`，而它们是互斥的。</span><span class="sxs-lookup"><span data-stu-id="5a75c-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a75c-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5a75c-104">To correct this error</span></span>  
  
-   <span data-ttu-id="5a75c-105">删除 `VbStrConv.SimplifiedChinese` 或 `VbStrConv.TraditionalChinese`。</span><span class="sxs-lookup"><span data-stu-id="5a75c-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a75c-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a75c-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="5a75c-107">基于 .NET Framework 的国际应用程序简介</span><span class="sxs-lookup"><span data-stu-id="5a75c-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
