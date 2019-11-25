---
title: 特性“<attributename>”不能应用多次
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968228"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="6a55d-102">特性 "\<attributename >" 不能应用多次</span><span class="sxs-lookup"><span data-stu-id="6a55d-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="6a55d-103">特性只能应用一次。</span><span class="sxs-lookup"><span data-stu-id="6a55d-103">The attribute can only be applied once.</span></span> <span data-ttu-id="6a55d-104">`AttributeUsage` 特性确定特性是否可以应用多次。</span><span class="sxs-lookup"><span data-stu-id="6a55d-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="6a55d-105">**错误 ID：** BC30663</span><span class="sxs-lookup"><span data-stu-id="6a55d-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6a55d-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6a55d-106">To correct this error</span></span>  
  
1. <span data-ttu-id="6a55d-107">请确保属性仅应用一次。</span><span class="sxs-lookup"><span data-stu-id="6a55d-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="6a55d-108">如果使用的是你开发的自定义特性，请考虑将其 `AttributeUsage` 特性更改为允许使用多种特性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6a55d-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a55d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a55d-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="6a55d-110">创建自定义特性</span><span class="sxs-lookup"><span data-stu-id="6a55d-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="6a55d-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="6a55d-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
