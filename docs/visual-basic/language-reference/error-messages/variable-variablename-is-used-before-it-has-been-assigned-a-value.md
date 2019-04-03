---
title: 变量“<variablename>”在赋值前被使用
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 46551a917aeb794c8d35985076b67a315386f628
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819354"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="e593c-102">变量\<变量名 > 在赋值前被使用</span><span class="sxs-lookup"><span data-stu-id="e593c-102">Variable '\<variablename>' is used before it has been assigned a value</span></span>
<span data-ttu-id="e593c-103">变量\<变量名 > 在赋值前被使用。</span><span class="sxs-lookup"><span data-stu-id="e593c-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="e593c-104">可能在运行时导致 null 引用异常。</span><span class="sxs-lookup"><span data-stu-id="e593c-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="e593c-105">应用程序能够通过其代码，用于读取变量之前为其分配任何值至少一个可能的路径。</span><span class="sxs-lookup"><span data-stu-id="e593c-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="e593c-106">如果从未为变量赋值，则它保持其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="e593c-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="e593c-107">对于引用数据类型，默认值是 [Nothing](../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="e593c-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="e593c-108">在某些情况下，读取具有 `Nothing` 值的引用变量可能导致 <xref:System.NullReferenceException> 。</span><span class="sxs-lookup"><span data-stu-id="e593c-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="e593c-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="e593c-109">By default, this message is a warning.</span></span> <span data-ttu-id="e593c-110">有关隐藏警告或将警告视为错误的详细信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="e593c-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e593c-111">**错误 ID:** BC42104</span><span class="sxs-lookup"><span data-stu-id="e593c-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e593c-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e593c-112">To correct this error</span></span>  
  
-   <span data-ttu-id="e593c-113">检查控制流逻辑，并确保该变量具有有效的值，控制权将传递给读取它的任何语句之前。</span><span class="sxs-lookup"><span data-stu-id="e593c-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="e593c-114">若要保证变量始终具有有效的值的一种方法是初始化其作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="e593c-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="e593c-115">请参阅中的"初始化" [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e593c-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e593c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e593c-116">See also</span></span>

- [<span data-ttu-id="e593c-117">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="e593c-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="e593c-118">变量声明</span><span class="sxs-lookup"><span data-stu-id="e593c-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e593c-119">变量疑难解答</span><span class="sxs-lookup"><span data-stu-id="e593c-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
