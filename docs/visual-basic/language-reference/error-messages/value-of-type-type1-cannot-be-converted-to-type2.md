---
title: "值的类型 &#39; type1 &#39;不能转换为 &#39; type2 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords: BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="2cdd8-102">值的类型 &#39; type1 &#39;不能转换为 &#39; type2 &#39;</span><span class="sxs-lookup"><span data-stu-id="2cdd8-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="2cdd8-103">类型 type1 的值无法转换到 type2。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="2cdd8-104">你可以使用 Value 属性来获取的第一个元素的字符串值\<parentElement >。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="2cdd8-105">已尝试将 XML 文本隐式强制转换为特定类型。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="2cdd8-106">XML 文本不能隐式强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="2cdd8-107">**错误 ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="2cdd8-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2cdd8-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2cdd8-108">To correct this error</span></span>  
  
-   <span data-ttu-id="2cdd8-109">使用 XML 文本的 `Value` 属性来将其值作为 `String`引用。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="2cdd8-110">使用 `CType` 函数、另一个类型转换函数，或 <xref:System.Convert> 类将值强制转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="2cdd8-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdd8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cdd8-111">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="2cdd8-112">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="2cdd8-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="2cdd8-113">XML 文本</span><span class="sxs-lookup"><span data-stu-id="2cdd8-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="2cdd8-114">XML</span><span class="sxs-lookup"><span data-stu-id="2cdd8-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
