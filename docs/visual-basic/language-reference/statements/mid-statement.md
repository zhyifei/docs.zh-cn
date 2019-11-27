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
ms.openlocfilehash: eeef4c13743b75a3d5e61ac46afb94d9ea105b7a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348024"
---
# <a name="mid-statement"></a><span data-ttu-id="bfcdd-102">Mid 语句</span><span class="sxs-lookup"><span data-stu-id="bfcdd-102">Mid Statement</span></span>
<span data-ttu-id="bfcdd-103">使用另一个字符串中的字符替换 `String` 变量中指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfcdd-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfcdd-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="bfcdd-105">部件</span><span class="sxs-lookup"><span data-stu-id="bfcdd-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="bfcdd-106">必需。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-106">Required.</span></span> <span data-ttu-id="bfcdd-107">要修改的 `String` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="bfcdd-108">必需。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-108">Required.</span></span> <span data-ttu-id="bfcdd-109">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-109">`Integer` expression.</span></span> <span data-ttu-id="bfcdd-110">`Target` 中开始替换文本的字符位置。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="bfcdd-111">`Start` 使用从1开始的索引。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="bfcdd-112">可选。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-112">Optional.</span></span> <span data-ttu-id="bfcdd-113">`Integer` 表达式。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-113">`Integer` expression.</span></span> <span data-ttu-id="bfcdd-114">要替换的字符数。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-114">Number of characters to replace.</span></span> <span data-ttu-id="bfcdd-115">如果省略，则使用所有 `String`。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="bfcdd-116">必需。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-116">Required.</span></span> <span data-ttu-id="bfcdd-117">替换 `Target`的一部分的 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="bfcdd-118">异常</span><span class="sxs-lookup"><span data-stu-id="bfcdd-118">Exceptions</span></span>  
  
|<span data-ttu-id="bfcdd-119">例外狀況類型</span><span class="sxs-lookup"><span data-stu-id="bfcdd-119">Exception type</span></span>|<span data-ttu-id="bfcdd-120">条件</span><span class="sxs-lookup"><span data-stu-id="bfcdd-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="bfcdd-121">`Start` < = 0 或 `Length` < 0。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfcdd-122">备注</span><span class="sxs-lookup"><span data-stu-id="bfcdd-122">Remarks</span></span>  
 <span data-ttu-id="bfcdd-123">替换的字符数始终小于或等于 `Target`中的字符数。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="bfcdd-124">Visual Basic 具有 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 函数和 `Mid` 语句。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="bfcdd-125">这些元素对字符串中的指定数量的字符进行操作，但 `Mid` 函数返回字符，而 `Mid` 语句替换这些字符。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="bfcdd-126">有关详细信息，请参阅 <xref:Microsoft.VisualBasic.Strings.Mid%2A>。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bfcdd-127">Visual Basic 早期版本的 `MidB` 语句将以字节而不是字符来替换子字符串。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="bfcdd-128">它主要用于在双字节字符集（DBCS）应用程序中转换字符串。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="bfcdd-129">所有 Visual Basic 字符串均采用 Unicode 格式，`MidB` 不再受支持。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfcdd-130">示例</span><span class="sxs-lookup"><span data-stu-id="bfcdd-130">Example</span></span>  
 <span data-ttu-id="bfcdd-131">此示例使用 `Mid` 语句将字符串变量中指定数量的字符替换为另一个字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="bfcdd-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="bfcdd-132">要求</span><span class="sxs-lookup"><span data-stu-id="bfcdd-132">Requirements</span></span>  
 <span data-ttu-id="bfcdd-133">**命名空间：** [Microsoft](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="bfcdd-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="bfcdd-134">**模块：** `Strings`</span><span class="sxs-lookup"><span data-stu-id="bfcdd-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="bfcdd-135">**程序集：** Visual Basic 运行时库（在 Microsoft. .dll 中）</span><span class="sxs-lookup"><span data-stu-id="bfcdd-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfcdd-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfcdd-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="bfcdd-137">字符串</span><span class="sxs-lookup"><span data-stu-id="bfcdd-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="bfcdd-138">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="bfcdd-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
