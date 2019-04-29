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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774811"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="3f544-102">类型“type1”的值无法转换为“type2”</span><span class="sxs-lookup"><span data-stu-id="3f544-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="3f544-103">类型 type1 的值无法转换为 type2。</span><span class="sxs-lookup"><span data-stu-id="3f544-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="3f544-104">可以使用 Value 属性来获取第一个元素的字符串值\<parentElement >。</span><span class="sxs-lookup"><span data-stu-id="3f544-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="3f544-105">已尝试将 XML 文本隐式强制转换为特定类型。</span><span class="sxs-lookup"><span data-stu-id="3f544-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="3f544-106">XML 文本不能隐式强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="3f544-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="3f544-107">**错误 ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="3f544-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f544-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3f544-108">To correct this error</span></span>  
  
- <span data-ttu-id="3f544-109">使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。</span><span class="sxs-lookup"><span data-stu-id="3f544-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="3f544-110">使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="3f544-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f544-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f544-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="3f544-112">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="3f544-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="3f544-113">XML 文本</span><span class="sxs-lookup"><span data-stu-id="3f544-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="3f544-114">XML</span><span class="sxs-lookup"><span data-stu-id="3f544-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
