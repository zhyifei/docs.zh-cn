---
title: 类型“type1”的值无法转换为“type2”
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: c8480c6fab2bff931950ebc21d0a8affe3c41c66
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827141"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="b71a0-102">类型“type1”的值无法转换为“type2”</span><span class="sxs-lookup"><span data-stu-id="b71a0-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="b71a0-103">类型 type1 的值无法转换为 type2。</span><span class="sxs-lookup"><span data-stu-id="b71a0-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="b71a0-104">可以使用 Value 属性来获取第一个元素的字符串值\<parentElement >。</span><span class="sxs-lookup"><span data-stu-id="b71a0-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="b71a0-105">已尝试将 XML 文本隐式强制转换为特定类型。</span><span class="sxs-lookup"><span data-stu-id="b71a0-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="b71a0-106">XML 文本不能隐式强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="b71a0-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="b71a0-107">**错误 ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="b71a0-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b71a0-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b71a0-108">To correct this error</span></span>  
  
-   <span data-ttu-id="b71a0-109">使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。</span><span class="sxs-lookup"><span data-stu-id="b71a0-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="b71a0-110">使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="b71a0-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71a0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b71a0-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="b71a0-112">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="b71a0-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b71a0-113">XML 文本</span><span class="sxs-lookup"><span data-stu-id="b71a0-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b71a0-114">XML</span><span class="sxs-lookup"><span data-stu-id="b71a0-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
