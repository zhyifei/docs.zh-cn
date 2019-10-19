---
title: Mid 语句（Visual Basic）
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
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581480"
---
# <a name="mid-statement"></a><span data-ttu-id="52689-102">Mid 语句</span><span class="sxs-lookup"><span data-stu-id="52689-102">Mid Statement</span></span>
<span data-ttu-id="52689-103">使用另一个字符串中的字符替换 `String` 变量中指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="52689-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52689-104">语法</span><span class="sxs-lookup"><span data-stu-id="52689-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="52689-105">部件</span><span class="sxs-lookup"><span data-stu-id="52689-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="52689-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="52689-106">Required.</span></span> <span data-ttu-id="52689-107">要修改的 `String` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="52689-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="52689-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="52689-108">Required.</span></span> <span data-ttu-id="52689-109">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="52689-109">`Integer` expression.</span></span> <span data-ttu-id="52689-110">@No__t_0 中开始替换文本的字符位置。</span><span class="sxs-lookup"><span data-stu-id="52689-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="52689-111">`Start` 使用从1开始的索引。</span><span class="sxs-lookup"><span data-stu-id="52689-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="52689-112">可选。</span><span class="sxs-lookup"><span data-stu-id="52689-112">Optional.</span></span> <span data-ttu-id="52689-113">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="52689-113">`Integer` expression.</span></span> <span data-ttu-id="52689-114">要替换的字符数。</span><span class="sxs-lookup"><span data-stu-id="52689-114">Number of characters to replace.</span></span> <span data-ttu-id="52689-115">如果省略，则使用所有 `String`。</span><span class="sxs-lookup"><span data-stu-id="52689-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="52689-116">必须的。</span><span class="sxs-lookup"><span data-stu-id="52689-116">Required.</span></span> <span data-ttu-id="52689-117">替换 `Target` 的一部分的 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="52689-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="52689-118">异常</span><span class="sxs-lookup"><span data-stu-id="52689-118">Exceptions</span></span>  
  
|<span data-ttu-id="52689-119">异常类型</span><span class="sxs-lookup"><span data-stu-id="52689-119">Exception type</span></span>|<span data-ttu-id="52689-120">条件</span><span class="sxs-lookup"><span data-stu-id="52689-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="52689-121">`Start` < = 0 或 `Length` < 0。</span><span class="sxs-lookup"><span data-stu-id="52689-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52689-122">备注</span><span class="sxs-lookup"><span data-stu-id="52689-122">Remarks</span></span>  
 <span data-ttu-id="52689-123">替换的字符数始终小于或等于 `Target` 中的字符数。</span><span class="sxs-lookup"><span data-stu-id="52689-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="52689-124">Visual Basic 具有 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 函数和 `Mid` 语句。</span><span class="sxs-lookup"><span data-stu-id="52689-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="52689-125">这些元素对字符串中的指定数量的字符进行操作，但 `Mid` 函数返回字符，而 `Mid` 语句替换这些字符。</span><span class="sxs-lookup"><span data-stu-id="52689-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="52689-126">有关更多信息，请参见<xref:Microsoft.VisualBasic.Strings.Mid%2A>。</span><span class="sxs-lookup"><span data-stu-id="52689-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52689-127">Visual Basic 早期版本的 `MidB` 语句将以字节而不是字符来替换子字符串。</span><span class="sxs-lookup"><span data-stu-id="52689-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="52689-128">它主要用于在双字节字符集（DBCS）应用程序中转换字符串。</span><span class="sxs-lookup"><span data-stu-id="52689-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="52689-129">所有 Visual Basic 字符串均采用 Unicode 格式，`MidB` 不再受支持。</span><span class="sxs-lookup"><span data-stu-id="52689-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52689-130">示例</span><span class="sxs-lookup"><span data-stu-id="52689-130">Example</span></span>  
 <span data-ttu-id="52689-131">此示例使用 `Mid` 语句将字符串变量中指定数量的字符替换为另一个字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="52689-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="52689-132">要求</span><span class="sxs-lookup"><span data-stu-id="52689-132">Requirements</span></span>  
 <span data-ttu-id="52689-133">**命名空间：** [Microsoft](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="52689-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="52689-134">**模块：** `Strings`</span><span class="sxs-lookup"><span data-stu-id="52689-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="52689-135">**程序集：** Visual Basic 运行时库（在 Microsoft. .dll 中）</span><span class="sxs-lookup"><span data-stu-id="52689-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52689-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="52689-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="52689-137">字符串</span><span class="sxs-lookup"><span data-stu-id="52689-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="52689-138">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="52689-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
