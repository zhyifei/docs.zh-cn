---
title: "结束&lt;关键字&gt;语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.EndDefinition
helpviewer_keywords: End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf0ac1221f8a85a8a43599d9c5ec210884205e5e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="50326-102">结束&lt;关键字&gt;语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50326-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>
<span data-ttu-id="50326-103">在后面带有其他关键字，终止引起该关键字的语句块的定义。</span><span class="sxs-lookup"><span data-stu-id="50326-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50326-104">语法</span><span class="sxs-lookup"><span data-stu-id="50326-104">Syntax</span></span>  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="50326-105">部件</span><span class="sxs-lookup"><span data-stu-id="50326-105">Parts</span></span>  
 `End`  
 <span data-ttu-id="50326-106">必需。</span><span class="sxs-lookup"><span data-stu-id="50326-106">Required.</span></span> <span data-ttu-id="50326-107">终止编程元素的定义。</span><span class="sxs-lookup"><span data-stu-id="50326-107">Terminates the definition of the programming element.</span></span>  
  
 `AddHandler`  
 <span data-ttu-id="50326-108">必选`AddHandler`访问器是匹配的开始`AddHandler`中自定义语句[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-108">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Class`  
 <span data-ttu-id="50326-109">必选的类定义是匹配的开始[类语句](../../../visual-basic/language-reference/statements/class-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-109">Required to terminate a class definition begun by a matching [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
 `Enum`  
 <span data-ttu-id="50326-110">必选枚举定义是匹配的开始[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-110">Required to terminate an enumeration definition begun by a matching [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 `Event`  
 <span data-ttu-id="50326-111">必选`Custom`是匹配的开始事件定义[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-111">Required to terminate a `Custom` event definition begun by a matching [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Function`  
 <span data-ttu-id="50326-112">必选`Function`过程定义是匹配的开始[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-112">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="50326-113">如果执行时遇到`End``Function`语句，控制权返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="50326-113">If execution encounters an `End``Function` statement, control returns to the calling code.</span></span>  
  
 `Get`  
 <span data-ttu-id="50326-114">必选`Property`过程定义是匹配的开始[Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-114">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md).</span></span> <span data-ttu-id="50326-115">如果执行时遇到`End``Get`语句，控制权返回给请求的属性值的语句。</span><span class="sxs-lookup"><span data-stu-id="50326-115">If execution encounters an `End``Get` statement, control returns to the statement requesting the property's value.</span></span>  
  
 `If`  
 <span data-ttu-id="50326-116">必选`If`...`Then`...`Else`阻止定义是匹配的开始`If`语句。</span><span class="sxs-lookup"><span data-stu-id="50326-116">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="50326-117">请参阅[如果...然后...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-117">See [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span>  
  
 `Interface`  
 <span data-ttu-id="50326-118">必选开始是匹配的接口定义[接口语句](../../../visual-basic/language-reference/statements/interface-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-118">Required to terminate an interface definition begun by a matching [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md).</span></span>  
  
 `Module`  
 <span data-ttu-id="50326-119">必选是匹配的开始的模块定义[模块语句](../../../visual-basic/language-reference/statements/module-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-119">Required to terminate a module definition begun by a matching [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
 `Namespace`  
 <span data-ttu-id="50326-120">必选命名空间定义是匹配的开始[Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-120">Required to terminate a namespace definition begun by a matching [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span>  
  
 `Operator`  
 <span data-ttu-id="50326-121">必选开始是匹配的运算符定义[Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-121">Required to terminate an operator definition begun by a matching [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 `Property`  
 <span data-ttu-id="50326-122">必选开始是匹配的属性定义[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-122">Required to terminate a property definition begun by a matching [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
 `RaiseEvent`  
 <span data-ttu-id="50326-123">必选`RaiseEvent`访问器是匹配的开始`RaiseEvent`中自定义语句[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-123">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `RemoveHandler`  
 <span data-ttu-id="50326-124">必选`RemoveHandler`访问器是匹配的开始`RemoveHandler`中自定义语句[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-124">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
 `Select`  
 <span data-ttu-id="50326-125">必选`Select`...`Case`阻止定义是匹配的开始`Select`语句。</span><span class="sxs-lookup"><span data-stu-id="50326-125">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="50326-126">请参阅[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-126">See [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
 `Set`  
 <span data-ttu-id="50326-127">必选`Property`过程定义是匹配的开始[Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-127">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md).</span></span> <span data-ttu-id="50326-128">如果执行时遇到`End``Set`语句，控制权返回给语句设置该属性的值。</span><span class="sxs-lookup"><span data-stu-id="50326-128">If execution encounters an `End``Set` statement, control returns to the statement setting the property's value.</span></span>  
  
 `Structure`  
 <span data-ttu-id="50326-129">必选是匹配的开始的结构定义[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-129">Required to terminate a structure definition begun by a matching [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
 `Sub`  
 <span data-ttu-id="50326-130">必选`Sub`过程定义是匹配的开始[Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-130">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span> <span data-ttu-id="50326-131">如果执行时遇到`End``Sub`语句，控制权返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="50326-131">If execution encounters an `End``Sub` statement, control returns to the calling code.</span></span>  
  
 `SyncLock`  
 <span data-ttu-id="50326-132">必选`SyncLock`阻止定义是匹配的开始`SyncLock`语句。</span><span class="sxs-lookup"><span data-stu-id="50326-132">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="50326-133">请参阅[SyncLock 语句](../../../visual-basic/language-reference/statements/synclock-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-133">See [SyncLock Statement](../../../visual-basic/language-reference/statements/synclock-statement.md).</span></span>  
  
 `Try`  
 <span data-ttu-id="50326-134">必选`Try`...`Catch`...`Finally`阻止定义是匹配的开始`Try`语句。</span><span class="sxs-lookup"><span data-stu-id="50326-134">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="50326-135">请参阅[重试...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-135">See [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 `While`  
 <span data-ttu-id="50326-136">必选`While`循环定义是匹配的开始`While`语句。</span><span class="sxs-lookup"><span data-stu-id="50326-136">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="50326-137">请参阅[时...While 语句结束](../../../visual-basic/language-reference/statements/while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-137">See [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
 `With`  
 <span data-ttu-id="50326-138">必选`With`阻止定义是匹配的开始`With`语句。</span><span class="sxs-lookup"><span data-stu-id="50326-138">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="50326-139">请参阅[与...使用语句结束](../../../visual-basic/language-reference/statements/with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-139">See [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50326-140">备注</span><span class="sxs-lookup"><span data-stu-id="50326-140">Remarks</span></span>  
 <span data-ttu-id="50326-141">[End 语句](../../../visual-basic/language-reference/statements/end-statement.md)，没有其他关键字时，执行会立即终止。</span><span class="sxs-lookup"><span data-stu-id="50326-141">The [End Statement](../../../visual-basic/language-reference/statements/end-statement.md), without an additional keyword, terminates execution immediately.</span></span>  
  
 <span data-ttu-id="50326-142">当跟在数字符号 (`#`)，则`End`关键字终止由相应的指令引入的预处理块。</span><span class="sxs-lookup"><span data-stu-id="50326-142">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  
  
 `#End`  
 <span data-ttu-id="50326-143">必需。</span><span class="sxs-lookup"><span data-stu-id="50326-143">Required.</span></span> <span data-ttu-id="50326-144">终止预处理块的定义。</span><span class="sxs-lookup"><span data-stu-id="50326-144">Terminates the definition of the preprocessing block.</span></span>  
  
 `#ExternalSource`  
 <span data-ttu-id="50326-145">必选开始是匹配的外部源块[#ExternalSource 指令](../../../visual-basic/language-reference/directives/externalsource-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-145">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md).</span></span>  
  
 `#If`  
 <span data-ttu-id="50326-146">必选开始是匹配的条件编译块`#If`指令。</span><span class="sxs-lookup"><span data-stu-id="50326-146">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="50326-147">请参阅[#If......#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-147">See [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md).</span></span>  
  
 `#Region`  
 <span data-ttu-id="50326-148">必选开始是匹配的源区域块[#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="50326-148">Required to terminate a source region block begun by a matching [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md).</span></span>  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="50326-149">智能设备的开发人员说明</span><span class="sxs-lookup"><span data-stu-id="50326-149">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="50326-150">`End`不支持语句，而无需其他关键字。</span><span class="sxs-lookup"><span data-stu-id="50326-150">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50326-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50326-151">See Also</span></span>  
 [<span data-ttu-id="50326-152">End 语句</span><span class="sxs-lookup"><span data-stu-id="50326-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
