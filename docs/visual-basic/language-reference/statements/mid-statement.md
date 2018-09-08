---
title: Mid 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44209350"
---
# <a name="mid-statement"></a><span data-ttu-id="4cf47-102">Mid 语句</span><span class="sxs-lookup"><span data-stu-id="4cf47-102">Mid Statement</span></span>
<span data-ttu-id="4cf47-103">替换指定的数目的中的字符`String`变量与另一字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="4cf47-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf47-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cf47-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="4cf47-105">部件</span><span class="sxs-lookup"><span data-stu-id="4cf47-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="4cf47-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="4cf47-106">Required.</span></span> <span data-ttu-id="4cf47-107">名称`String`变量来修改。</span><span class="sxs-lookup"><span data-stu-id="4cf47-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="4cf47-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="4cf47-108">Required.</span></span> <span data-ttu-id="4cf47-109">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="4cf47-109">`Integer` expression.</span></span> <span data-ttu-id="4cf47-110">字符位置`Target`文本替换的开始位置。</span><span class="sxs-lookup"><span data-stu-id="4cf47-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="4cf47-111">`Start` 使用从 1 开始的索引。</span><span class="sxs-lookup"><span data-stu-id="4cf47-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="4cf47-112">可选。</span><span class="sxs-lookup"><span data-stu-id="4cf47-112">Optional.</span></span> <span data-ttu-id="4cf47-113">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="4cf47-113">`Integer` expression.</span></span> <span data-ttu-id="4cf47-114">要替换的字符数。</span><span class="sxs-lookup"><span data-stu-id="4cf47-114">Number of characters to replace.</span></span> <span data-ttu-id="4cf47-115">如果省略，所有的`String`使用。</span><span class="sxs-lookup"><span data-stu-id="4cf47-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="4cf47-116">必须的。</span><span class="sxs-lookup"><span data-stu-id="4cf47-116">Required.</span></span> <span data-ttu-id="4cf47-117">`String` 替换的一部分的表达式`Target`。</span><span class="sxs-lookup"><span data-stu-id="4cf47-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="4cf47-118">异常</span><span class="sxs-lookup"><span data-stu-id="4cf47-118">Exceptions</span></span>  
  
|<span data-ttu-id="4cf47-119">异常类型</span><span class="sxs-lookup"><span data-stu-id="4cf47-119">Exception type</span></span>|<span data-ttu-id="4cf47-120">条件</span><span class="sxs-lookup"><span data-stu-id="4cf47-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="4cf47-121">`Start` < = 0 或`Length`< 0。</span><span class="sxs-lookup"><span data-stu-id="4cf47-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cf47-122">备注</span><span class="sxs-lookup"><span data-stu-id="4cf47-122">Remarks</span></span>  
 <span data-ttu-id="4cf47-123">替换的字符数是始终小于或等于中的字符数`Target`。</span><span class="sxs-lookup"><span data-stu-id="4cf47-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="4cf47-124">Visual Basic 具有<xref:Microsoft.VisualBasic.Strings.Mid%2A>函数和一个`Mid`语句。</span><span class="sxs-lookup"><span data-stu-id="4cf47-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="4cf47-125">都按指定数目的字符在字符串中，运行这些元素，但`Mid`函数将返回字符，而`Mid`语句替换的字符。</span><span class="sxs-lookup"><span data-stu-id="4cf47-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="4cf47-126">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Strings.Mid%2A>。</span><span class="sxs-lookup"><span data-stu-id="4cf47-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cf47-127">`MidB`的早期版本的 Visual Basic 语句将替换中字节，而不是字符的子字符串。</span><span class="sxs-lookup"><span data-stu-id="4cf47-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="4cf47-128">它主要用于在双字节字符集 (DBCS) 应用程序中转换字符串。</span><span class="sxs-lookup"><span data-stu-id="4cf47-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="4cf47-129">所有 Visual Basic 字符串都是 Unicode，和`MidB`不再受支持。</span><span class="sxs-lookup"><span data-stu-id="4cf47-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf47-130">示例</span><span class="sxs-lookup"><span data-stu-id="4cf47-130">Example</span></span>  
 <span data-ttu-id="4cf47-131">此示例使用`Mid`语句，以指定的数量的字符串变量中的字符替换为另一字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="4cf47-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="4cf47-132">要求</span><span class="sxs-lookup"><span data-stu-id="4cf47-132">Requirements</span></span>  
 <span data-ttu-id="4cf47-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="4cf47-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="4cf47-134">**模块：** `Strings`</span><span class="sxs-lookup"><span data-stu-id="4cf47-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="4cf47-135">**程序集：** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cf47-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf47-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cf47-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="4cf47-137">字符串</span><span class="sxs-lookup"><span data-stu-id="4cf47-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="4cf47-138">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="4cf47-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
