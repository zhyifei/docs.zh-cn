---
title: 不能组合 VbStrConv.Wide 和 VbStrConv.Narrow
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 0d41e283b103d0a1b585cbf686b66d64f47ed22d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723269"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="4408a-102">不能组合 VbStrConv.Wide 和 VbStrConv.Narrow</span><span class="sxs-lookup"><span data-stu-id="4408a-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="4408a-103">你的应用程序尝试组合 `VbStrConv` 枚举成员 `Wide` 和 `Narrow`，而它们是互斥的。</span><span class="sxs-lookup"><span data-stu-id="4408a-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4408a-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4408a-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4408a-105">删除 `VbStrConv.Wide` 或 `VbStrConv.Narrow`。</span><span class="sxs-lookup"><span data-stu-id="4408a-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4408a-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="4408a-106">See also</span></span>
- <xref:System.Globalization>

- [<span data-ttu-id="4408a-107">基于 .NET Framework 的国际应用程序简介</span><span class="sxs-lookup"><span data-stu-id="4408a-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
