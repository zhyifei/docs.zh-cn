---
title: System.Convert 方法
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: 0d98d159c24e1a47723aeb07a9654fe22b1d9464
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198213"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="b412a-102">System.Convert 方法</span><span class="sxs-lookup"><span data-stu-id="b412a-102">System.Convert Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b412a-103">不支持以下<xref:System.Convert>方法。</span><span class="sxs-lookup"><span data-stu-id="b412a-103">does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="b412a-104">带有 <xref:System.IFormatProvider> 参数的版本。</span><span class="sxs-lookup"><span data-stu-id="b412a-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="b412a-105">涉及字符数组或字节数组的方法：</span><span class="sxs-lookup"><span data-stu-id="b412a-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="b412a-106">以下方法：</span><span class="sxs-lookup"><span data-stu-id="b412a-106">The following methods:</span></span>  
  
    -   `public static <Type2> To<Type2>(<Type1> value);` <span data-ttu-id="b412a-107">其中</span><span class="sxs-lookup"><span data-stu-id="b412a-107">where</span></span>  
  
         `Type1` <span data-ttu-id="b412a-108">并`Type2`是每个`sbyte`， `uint`， `ulong`，或`ushort`。</span><span class="sxs-lookup"><span data-stu-id="b412a-108">and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="b412a-109">C#：</span><span class="sxs-lookup"><span data-stu-id="b412a-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="b412a-110">Visual Basic：</span><span class="sxs-lookup"><span data-stu-id="b412a-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="b412a-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b412a-111">See also</span></span>

- [<span data-ttu-id="b412a-112">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="b412a-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
