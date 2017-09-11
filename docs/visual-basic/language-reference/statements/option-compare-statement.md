---
title: "Option Compare 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
dev_langs:
- VB
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword
- binary comparison
- strings [Visual Basic], returning from functions
- binary comparison, Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword, Option Compare statement
- Binary keyword, Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 00618cd914c06b896d68b4074464af866f747895
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="option-compare-statement"></a><span data-ttu-id="a33da-102">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="a33da-102">Option Compare Statement</span></span>
<span data-ttu-id="a33da-103">声明比较字符串数据时要使用的默认比较方法。</span><span class="sxs-lookup"><span data-stu-id="a33da-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33da-104">语法</span><span class="sxs-lookup"><span data-stu-id="a33da-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="a33da-105">部件</span><span class="sxs-lookup"><span data-stu-id="a33da-105">Parts</span></span>  
  
|<span data-ttu-id="a33da-106">术语</span><span class="sxs-lookup"><span data-stu-id="a33da-106">Term</span></span>|<span data-ttu-id="a33da-107">定义</span><span class="sxs-lookup"><span data-stu-id="a33da-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="a33da-108">可选。</span><span class="sxs-lookup"><span data-stu-id="a33da-108">Optional.</span></span> <span data-ttu-id="a33da-109">字符串比较中的结果基于派生自字符的内部二进制表示形式排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a33da-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="a33da-110">这种比较类型在字符串包含不能解释为文本的字符时尤其有用。</span><span class="sxs-lookup"><span data-stu-id="a33da-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="a33da-111">在这种情况下，你不想因为字母顺序的等效性（如，不区分大小写）而使比较出现偏差。</span><span class="sxs-lookup"><span data-stu-id="a33da-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="a33da-112">可选。</span><span class="sxs-lookup"><span data-stu-id="a33da-112">Optional.</span></span> <span data-ttu-id="a33da-113">字符串比较中的结果基于由系统的区域设置确定的不区分大小写的文本排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a33da-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="a33da-114">如果字符串包含所有文本字符且你想在比较它们时考虑到母顺序等效性（如，不区分大小写和紧密相关的字母），则这种比较类型非常有用。</span><span class="sxs-lookup"><span data-stu-id="a33da-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="a33da-115">例如，你可能认定 `A` 等于 `a`，`Ä` 和 `ä` 出现在 `B` 和 `b` 之前。</span><span class="sxs-lookup"><span data-stu-id="a33da-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a33da-116">备注</span><span class="sxs-lookup"><span data-stu-id="a33da-116">Remarks</span></span>  
 <span data-ttu-id="a33da-117">使用时，`Option Compare` 语句必须在文件中任何其他源代码语句之前。</span><span class="sxs-lookup"><span data-stu-id="a33da-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="a33da-118">`Option Compare` 语句指定字符串比较方法（`Binary` 或 `Text`）。</span><span class="sxs-lookup"><span data-stu-id="a33da-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="a33da-119">默认的文本比较方法是 `Binary`。</span><span class="sxs-lookup"><span data-stu-id="a33da-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="a33da-120">`Binary` 比较会对每个字符串中每个字符的数字 Unicode 值进行比较。</span><span class="sxs-lookup"><span data-stu-id="a33da-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="a33da-121">`Text` 比较会基于当前区域性中的词汇意义对每个 Unicode 字符进行比较。</span><span class="sxs-lookup"><span data-stu-id="a33da-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="a33da-122">在 Microsoft Windows 中，排序顺序取决于代码页。</span><span class="sxs-lookup"><span data-stu-id="a33da-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="a33da-123">有关详细信息，请参阅[代码页](https://docs.microsoft.com/cpp/c-runtime-library/code-pages)。</span><span class="sxs-lookup"><span data-stu-id="a33da-123">For more information, see [Code Pages](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="a33da-124">在下例中，使用 `Option Compare Binary` 对英语/欧洲代码页 (ANSI 1252) 中的字符进行排序，由此产生典型的二进制排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a33da-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="a33da-125">使用 `Option Compare Text` 对同一代码页中的相同字符进行排序时，会产生以下文本排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a33da-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="a33da-126">当 Option Compare 语句不存在时</span><span class="sxs-lookup"><span data-stu-id="a33da-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="a33da-127">如果源代码不包含`Option Compare`语句， **Option Compare**上设置[编译页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="a33da-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="a33da-128">如果您使用命令行编译器，指定的设置[/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)使用编译器选项。</span><span class="sxs-lookup"><span data-stu-id="a33da-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="a33da-129">若要在 IDE 中设置 Option Compare</span><span class="sxs-lookup"><span data-stu-id="a33da-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="a33da-130">在**解决方案资源管理器**，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="a33da-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="a33da-131">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a33da-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="a33da-132">有关详细信息，请参阅[NIB︰ 使用项目设计器管理项目属性](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)。</span><span class="sxs-lookup"><span data-stu-id="a33da-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="a33da-133">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="a33da-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="a33da-134">中的值设置**Option Compare**框。</span><span class="sxs-lookup"><span data-stu-id="a33da-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="a33da-135">当您创建项目时， **Option Compare**上设置**编译**选项卡上设置为**Option Compare**中设置**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="a33da-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="a33da-136">若要更改此设置，请在**工具**菜单上，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="a33da-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="a33da-137">在**选项**对话框框中，展开**项目和解决方案**，然后单击**VB 默认值**。</span><span class="sxs-lookup"><span data-stu-id="a33da-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="a33da-138">中的初始默认设置**VB 默认值**是**二进制**。</span><span class="sxs-lookup"><span data-stu-id="a33da-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="a33da-139">若要设置命令行上的 Option Compare</span><span class="sxs-lookup"><span data-stu-id="a33da-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="a33da-140">包括[/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="a33da-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33da-141">示例</span><span class="sxs-lookup"><span data-stu-id="a33da-141">Example</span></span>  
 <span data-ttu-id="a33da-142">下例使用 `Option Compare` 语句将二进制比较设置为默认字符串比较方法。</span><span class="sxs-lookup"><span data-stu-id="a33da-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="a33da-143">若要使用此代码，请取消 `Option Compare Binary` 语句的注释，并将其置于源文件顶部。</span><span class="sxs-lookup"><span data-stu-id="a33da-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="a33da-144">[!code-vb[VbVbalrStatements #&45;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a33da-144">[!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33da-145">示例</span><span class="sxs-lookup"><span data-stu-id="a33da-145">Example</span></span>  
 <span data-ttu-id="a33da-146">下例使用 `Option Compare` 语句将不区分大小写的文本排序顺序设置为默认字符串比较方法。</span><span class="sxs-lookup"><span data-stu-id="a33da-146">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="a33da-147">若要使用此代码，请取消 `Option Compare Text` 语句的注释，并将其置于源文件顶部。</span><span class="sxs-lookup"><span data-stu-id="a33da-147">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="a33da-148">[!code-vb[VbVbalrStatements #&46;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a33da-148">[!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33da-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a33da-149">See Also</span></span>  
 <span data-ttu-id="a33da-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></xref:Microsoft.VisualBasic.Strings.InStr%2A></span><span class="sxs-lookup"><span data-stu-id="a33da-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></span></span>   
 <span data-ttu-id="a33da-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span><span class="sxs-lookup"><span data-stu-id="a33da-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span></span>   
 <span data-ttu-id="a33da-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></xref:Microsoft.VisualBasic.Strings.Replace%2A></span><span class="sxs-lookup"><span data-stu-id="a33da-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></span></span>   
 <span data-ttu-id="a33da-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="a33da-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="a33da-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></xref:Microsoft.VisualBasic.Strings.StrComp%2A></span><span class="sxs-lookup"><span data-stu-id="a33da-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></span></span>   
<span data-ttu-id="a33da-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="a33da-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="a33da-156"> [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="a33da-156"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="a33da-157"> [在 Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="a33da-157"> [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="a33da-158"> [Like 运算符](../../../visual-basic/language-reference/operators/like-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a33da-158"> [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span></span>  
<span data-ttu-id="a33da-159"> [字符串函数](../../../visual-basic/language-reference/functions/string-functions.md) </span><span class="sxs-lookup"><span data-stu-id="a33da-159"> [String Functions](../../../visual-basic/language-reference/functions/string-functions.md) </span></span>  
<span data-ttu-id="a33da-160"> [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a33da-160"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="a33da-161"> [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a33da-161"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
