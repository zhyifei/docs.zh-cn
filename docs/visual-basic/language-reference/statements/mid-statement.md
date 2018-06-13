---
title: Mid 语句
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
ms.openlocfilehash: 90b805df902dcdfebe85421583dd54e9af04bec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602260"
---
# <a name="mid-statement"></a><span data-ttu-id="f4092-102">Mid 语句</span><span class="sxs-lookup"><span data-stu-id="f4092-102">Mid Statement</span></span>
<span data-ttu-id="f4092-103">替换指定的数目的中的字符`String`变量与另一个字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="f4092-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4092-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4092-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="f4092-105">部件</span><span class="sxs-lookup"><span data-stu-id="f4092-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="f4092-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="f4092-106">Required.</span></span> <span data-ttu-id="f4092-107">名称`String`变量以修改。</span><span class="sxs-lookup"><span data-stu-id="f4092-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="f4092-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="f4092-108">Required.</span></span> <span data-ttu-id="f4092-109">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="f4092-109">`Integer` expression.</span></span> <span data-ttu-id="f4092-110">字符中的位置`Target`替换文本的起始位置。</span><span class="sxs-lookup"><span data-stu-id="f4092-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="f4092-111">`Start` 使用基于 1 的索引。</span><span class="sxs-lookup"><span data-stu-id="f4092-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="f4092-112">可选。</span><span class="sxs-lookup"><span data-stu-id="f4092-112">Optional.</span></span> <span data-ttu-id="f4092-113">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="f4092-113">`Integer` expression.</span></span> <span data-ttu-id="f4092-114">要替换的字符数。</span><span class="sxs-lookup"><span data-stu-id="f4092-114">Number of characters to replace.</span></span> <span data-ttu-id="f4092-115">如果省略，所有的`String`使用。</span><span class="sxs-lookup"><span data-stu-id="f4092-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="f4092-116">必须的。</span><span class="sxs-lookup"><span data-stu-id="f4092-116">Required.</span></span> <span data-ttu-id="f4092-117">`String` 替换的一部分的表达式`Target`。</span><span class="sxs-lookup"><span data-stu-id="f4092-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="f4092-118">异常</span><span class="sxs-lookup"><span data-stu-id="f4092-118">Exceptions</span></span>  
  
|<span data-ttu-id="f4092-119">异常类型</span><span class="sxs-lookup"><span data-stu-id="f4092-119">Exception type</span></span>|<span data-ttu-id="f4092-120">条件</span><span class="sxs-lookup"><span data-stu-id="f4092-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="f4092-121">`Start` < = 0 或`Length`< 0。</span><span class="sxs-lookup"><span data-stu-id="f4092-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4092-122">备注</span><span class="sxs-lookup"><span data-stu-id="f4092-122">Remarks</span></span>  
 <span data-ttu-id="f4092-123">替换的字符数是始终小于或等于的中的字符数`Target`。</span><span class="sxs-lookup"><span data-stu-id="f4092-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="f4092-124">Visual Basic 具有<xref:Microsoft.VisualBasic.Strings.Mid%2A>函数和`Mid`语句。</span><span class="sxs-lookup"><span data-stu-id="f4092-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="f4092-125">这些元素都指定数量的字符在字符串中，操作但`Mid`函数将返回字符，而`Mid`语句替换字符。</span><span class="sxs-lookup"><span data-stu-id="f4092-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="f4092-126">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Strings.Mid%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4092-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4092-127">`MidB`的早期版本的 Visual Basic 的语句替换字节，而不是字符的子字符串。</span><span class="sxs-lookup"><span data-stu-id="f4092-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="f4092-128">它主要用于在双字节字符集 (DBCS) 应用程序中转换字符串。</span><span class="sxs-lookup"><span data-stu-id="f4092-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="f4092-129">所有 Visual Basic 字符串都都以 unicode 格式，和`MidB`不再受支持。</span><span class="sxs-lookup"><span data-stu-id="f4092-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4092-130">示例</span><span class="sxs-lookup"><span data-stu-id="f4092-130">Example</span></span>  
 <span data-ttu-id="f4092-131">此示例使用`Mid`语句以将指定的数目的字符串变量中的字符替换为从另一个字符串的字符。</span><span class="sxs-lookup"><span data-stu-id="f4092-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="f4092-132">要求</span><span class="sxs-lookup"><span data-stu-id="f4092-132">Requirements</span></span>  
 <span data-ttu-id="f4092-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="f4092-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="f4092-134">**模块：** `Strings`</span><span class="sxs-lookup"><span data-stu-id="f4092-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="f4092-135">**程序集：** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4092-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4092-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4092-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="f4092-137">字符串</span><span class="sxs-lookup"><span data-stu-id="f4092-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="f4092-138">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="f4092-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
