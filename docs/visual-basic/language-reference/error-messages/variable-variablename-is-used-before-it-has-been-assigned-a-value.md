---
title: "变量&lt;variablename&gt;在赋值前被使用 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: dfc924ebbebb8b20654156b8871684dcfad6848a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="3420c-102">变量&lt;variablename&gt;在赋值前被使用</span><span class="sxs-lookup"><span data-stu-id="3420c-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="3420c-103">变量\<variablename&1;> 在赋值前被使用。</span><span class="sxs-lookup"><span data-stu-id="3420c-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="3420c-104">可能在运行时导致 null 引用异常。</span><span class="sxs-lookup"><span data-stu-id="3420c-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="3420c-105">应用程序具有至少一个可能读取变量之前的任何值分配给它的代码路径。</span><span class="sxs-lookup"><span data-stu-id="3420c-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="3420c-106">如果从未为变量赋值，则它保持其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="3420c-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="3420c-107">对于引用数据类型，该默认值是[Nothing](../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="3420c-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="3420c-108">读取的值为一个引用变量`Nothing`可能会导致<xref:System.NullReferenceException>在某些情况下。</xref:System.NullReferenceException></span><span class="sxs-lookup"><span data-stu-id="3420c-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="3420c-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="3420c-109">By default, this message is a warning.</span></span> <span data-ttu-id="3420c-110">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="3420c-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3420c-111">**错误 ID:** BC42104</span><span class="sxs-lookup"><span data-stu-id="3420c-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3420c-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3420c-112">To correct this error</span></span>  
  
-   <span data-ttu-id="3420c-113">控制流逻辑检查并确保在控件传递给读取它的任何语句之前，该变量具有有效的值。</span><span class="sxs-lookup"><span data-stu-id="3420c-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="3420c-114">若要确保该变量始终具有一个有效的值的一种方法是初始化为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="3420c-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="3420c-115">请参阅中的"初始化" [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3420c-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3420c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3420c-116">See Also</span></span>  
 <span data-ttu-id="3420c-117">[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3420c-117">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="3420c-118"> [变量声明](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="3420c-118"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="3420c-119"> [变量疑难解答](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span><span class="sxs-lookup"><span data-stu-id="3420c-119"> [Troubleshooting Variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span></span>
