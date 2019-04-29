---
title: 特性“<attributename>”不能应用多次
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935312"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="2bc78-102">属性 '\<attributename > 不能应用多次</span><span class="sxs-lookup"><span data-stu-id="2bc78-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="2bc78-103">该特性仅应用一次。</span><span class="sxs-lookup"><span data-stu-id="2bc78-103">The attribute can only be applied once.</span></span> <span data-ttu-id="2bc78-104">`AttributeUsage`属性确定是否可以多次应用属性。</span><span class="sxs-lookup"><span data-stu-id="2bc78-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="2bc78-105">**错误 ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="2bc78-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2bc78-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2bc78-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2bc78-107">请确保该属性只应用一次。</span><span class="sxs-lookup"><span data-stu-id="2bc78-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="2bc78-108">如果使用的您开发的自定义特性，请考虑更改其`AttributeUsage`属性以允许多个特性用法，与下面的示例一样。</span><span class="sxs-lookup"><span data-stu-id="2bc78-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2bc78-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bc78-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="2bc78-110">创建自定义特性</span><span class="sxs-lookup"><span data-stu-id="2bc78-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="2bc78-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="2bc78-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
