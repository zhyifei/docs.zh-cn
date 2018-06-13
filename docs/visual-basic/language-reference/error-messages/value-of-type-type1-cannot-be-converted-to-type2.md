---
title: 类型的值&#39;type1&#39;不能转换为&#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 9e59d3bc5e2bfca3628248d08ffc475334d4da79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602750"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="fb543-102">类型的值&#39;type1&#39;不能转换为&#39;type2&#39;</span><span class="sxs-lookup"><span data-stu-id="fb543-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="fb543-103">类型 type1 的值无法转换到 type2。</span><span class="sxs-lookup"><span data-stu-id="fb543-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="fb543-104">你可以使用 Value 属性来获取的第一个元素的字符串值\<parentElement >。</span><span class="sxs-lookup"><span data-stu-id="fb543-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="fb543-105">已尝试将 XML 文本隐式强制转换为特定类型。</span><span class="sxs-lookup"><span data-stu-id="fb543-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="fb543-106">XML 文本不能隐式强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="fb543-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="fb543-107">**错误 ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="fb543-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb543-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="fb543-108">To correct this error</span></span>  
  
-   <span data-ttu-id="fb543-109">使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。</span><span class="sxs-lookup"><span data-stu-id="fb543-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="fb543-110">使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="fb543-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb543-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb543-111">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="fb543-112">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="fb543-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="fb543-113">XML 文本</span><span class="sxs-lookup"><span data-stu-id="fb543-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="fb543-114">XML</span><span class="sxs-lookup"><span data-stu-id="fb543-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
