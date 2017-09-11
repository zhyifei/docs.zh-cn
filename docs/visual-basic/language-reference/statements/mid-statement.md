---
title: "Mid 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e94500c8bd7f2c6351c91ba028c1ad6d8d3dd4c3
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="mid-statement"></a><span data-ttu-id="54e7c-102">Mid 语句</span><span class="sxs-lookup"><span data-stu-id="54e7c-102">Mid Statement</span></span>
<span data-ttu-id="54e7c-103">替换中的字符数目为指定的数目`String`变量与另一个字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="54e7c-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="54e7c-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="54e7c-105">部件</span><span class="sxs-lookup"><span data-stu-id="54e7c-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="54e7c-106">必需。</span><span class="sxs-lookup"><span data-stu-id="54e7c-106">Required.</span></span> <span data-ttu-id="54e7c-107">名称`String`变量来修改。</span><span class="sxs-lookup"><span data-stu-id="54e7c-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="54e7c-108">必需。</span><span class="sxs-lookup"><span data-stu-id="54e7c-108">Required.</span></span> <span data-ttu-id="54e7c-109">`Integer`表达式。</span><span class="sxs-lookup"><span data-stu-id="54e7c-109">`Integer` expression.</span></span> <span data-ttu-id="54e7c-110">字符位置`Target`替换文本的开始位置。</span><span class="sxs-lookup"><span data-stu-id="54e7c-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="54e7c-111">`Start`使用从&1; 开始的索引。</span><span class="sxs-lookup"><span data-stu-id="54e7c-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="54e7c-112">可选。</span><span class="sxs-lookup"><span data-stu-id="54e7c-112">Optional.</span></span> <span data-ttu-id="54e7c-113">`Integer`表达式。</span><span class="sxs-lookup"><span data-stu-id="54e7c-113">`Integer` expression.</span></span> <span data-ttu-id="54e7c-114">要替换的字符数。</span><span class="sxs-lookup"><span data-stu-id="54e7c-114">Number of characters to replace.</span></span> <span data-ttu-id="54e7c-115">如果省略，所有`String`使用。</span><span class="sxs-lookup"><span data-stu-id="54e7c-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="54e7c-116">必需。</span><span class="sxs-lookup"><span data-stu-id="54e7c-116">Required.</span></span> <span data-ttu-id="54e7c-117">`String`替换的一部分的表达式`Target`。</span><span class="sxs-lookup"><span data-stu-id="54e7c-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="54e7c-118">异常</span><span class="sxs-lookup"><span data-stu-id="54e7c-118">Exceptions</span></span>  
  
|<span data-ttu-id="54e7c-119">异常类型</span><span class="sxs-lookup"><span data-stu-id="54e7c-119">Exception type</span></span>|<span data-ttu-id="54e7c-120">条件</span><span class="sxs-lookup"><span data-stu-id="54e7c-120">Condition</span></span>|  
|--------------------|---------------|  
|<span data-ttu-id="54e7c-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="54e7c-121"><xref:System.ArgumentException></span></span>|<span data-ttu-id="54e7c-122">`Start`<= 0="" or=""></=>`Length`< 0.></ 0.></span><span class="sxs-lookup"><span data-stu-id="54e7c-122">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54e7c-123">备注</span><span class="sxs-lookup"><span data-stu-id="54e7c-123">Remarks</span></span>  
 <span data-ttu-id="54e7c-124">替换的字符数是始终小于或等于中的字符数`Target`。</span><span class="sxs-lookup"><span data-stu-id="54e7c-124">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="54e7c-125">Visual Basic 具有<xref:Microsoft.VisualBasic.Strings.Mid%2A>函数和一个`Mid`语句。</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="54e7c-125">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="54e7c-126">这些元素都指定数量的字符在字符串中，操作但`Mid`函数将返回字符，而`Mid`语句替换字符。</span><span class="sxs-lookup"><span data-stu-id="54e7c-126">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="54e7c-127">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Strings.Mid%2A>。</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="54e7c-127">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54e7c-128">`MidB`的早期版本的 Visual Basic 语句替换中字节，而不是字符的子字符串。</span><span class="sxs-lookup"><span data-stu-id="54e7c-128">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="54e7c-129">它主要用于在双字节字符集 (DBCS) 应用程序中转换字符串。</span><span class="sxs-lookup"><span data-stu-id="54e7c-129">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="54e7c-130">所有 Visual Basic 字符串都并以 unicode 格式，并`MidB`不再受支持。</span><span class="sxs-lookup"><span data-stu-id="54e7c-130">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54e7c-131">示例</span><span class="sxs-lookup"><span data-stu-id="54e7c-131">Example</span></span>  
 <span data-ttu-id="54e7c-132">此示例使用`Mid`语句，以将指定的数目的字符串变量中的字符替换为另一个字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="54e7c-132">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 <span data-ttu-id="54e7c-133">[!code-vb[VbVbalrStrings #&5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="54e7c-133">[!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e7c-134">要求</span><span class="sxs-lookup"><span data-stu-id="54e7c-134">Requirements</span></span>  
 <span data-ttu-id="54e7c-135">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="54e7c-135">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="54e7c-136">**模块︰**`Strings`</span><span class="sxs-lookup"><span data-stu-id="54e7c-136">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="54e7c-137">**程序集︰**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e7c-137">**Assembly:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e7c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54e7c-138">See Also</span></span>  
 <span data-ttu-id="54e7c-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="54e7c-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
<span data-ttu-id="54e7c-140"> [字符串](../../../visual-basic/programming-guide/language-features/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="54e7c-140"> [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md) </span></span>  
<span data-ttu-id="54e7c-141"> [在 Visual Basic 中字符串的简介](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="54e7c-141"> [Introduction to Strings in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
