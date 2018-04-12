---
title: 变量 &#39;&lt;variablename&gt;&#39; 在赋值前被使用
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 201667c250e15bb9af73e64e2d8c924c1952d1be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="8292f-102">变量 &#39;&lt;variablename&gt;&#39; 在赋值前被使用</span><span class="sxs-lookup"><span data-stu-id="8292f-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="8292f-103">变量\<variablename > 在赋值前被使用。</span><span class="sxs-lookup"><span data-stu-id="8292f-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="8292f-104">可能在运行时导致 null 引用异常。</span><span class="sxs-lookup"><span data-stu-id="8292f-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="8292f-105">应用程序具有至少一个通过其读取变量，然后才能任何值分配给它的代码可能路径。</span><span class="sxs-lookup"><span data-stu-id="8292f-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="8292f-106">如果从未为变量赋值，则它保持其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="8292f-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="8292f-107">对于引用数据类型，默认值是[执行任何操作](../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="8292f-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="8292f-108">在某些情况下，读取具有 `Nothing` 值的引用变量可能导致 <xref:System.NullReferenceException> 。</span><span class="sxs-lookup"><span data-stu-id="8292f-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="8292f-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="8292f-109">By default, this message is a warning.</span></span> <span data-ttu-id="8292f-110">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="8292f-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8292f-111">**错误 ID:** BC42104</span><span class="sxs-lookup"><span data-stu-id="8292f-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8292f-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8292f-112">To correct this error</span></span>  
  
-   <span data-ttu-id="8292f-113">请检查控制流逻辑并确保该变量具有有效的值，在控件传递给读取它的任何语句之前。</span><span class="sxs-lookup"><span data-stu-id="8292f-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="8292f-114">若要确保该变量始终具有一个有效的值的一种方法是初始化其作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="8292f-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="8292f-115">请参阅中的"初始化" [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="8292f-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8292f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8292f-116">See Also</span></span>  
 [<span data-ttu-id="8292f-117">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="8292f-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="8292f-118">变量声明</span><span class="sxs-lookup"><span data-stu-id="8292f-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="8292f-119">变量疑难解答</span><span class="sxs-lookup"><span data-stu-id="8292f-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
