---
title: End <keyword> 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 96dc8ce6b0d3b7545f5caeef43358936e426f566
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273525"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="90a56-102">结束\<关键字 > 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90a56-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="90a56-103">在后面带有其他关键字，终止由该关键字引入的语句块的定义。</span><span class="sxs-lookup"><span data-stu-id="90a56-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="90a56-104">语法</span><span class="sxs-lookup"><span data-stu-id="90a56-104">Syntax</span></span>

```vb
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
  
## <a name="parts"></a><span data-ttu-id="90a56-105">部件</span><span class="sxs-lookup"><span data-stu-id="90a56-105">Parts</span></span>

|<span data-ttu-id="90a56-106">部件</span><span class="sxs-lookup"><span data-stu-id="90a56-106">Part</span></span>|<span data-ttu-id="90a56-107">描述</span><span class="sxs-lookup"><span data-stu-id="90a56-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="90a56-108">必需。</span><span class="sxs-lookup"><span data-stu-id="90a56-108">Required.</span></span> <span data-ttu-id="90a56-109">终止编程元素的定义。</span><span class="sxs-lookup"><span data-stu-id="90a56-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="90a56-110">必选`AddHandler`访问器是匹配的开始`AddHandler`语句在自定义[Event 语句](event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="90a56-111">类定义开始是匹配的必选[Class 语句](class-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="90a56-112">枚举定义开始是匹配的必选[Enum 语句](enum-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="90a56-113">必选`Custom`是匹配的开始事件定义[Event 语句](event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="90a56-114">必选`Function`过程定义是匹配的开始[Function 语句](function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="90a56-115">如果执行时遇到`End Function`语句，控件返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="90a56-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="90a56-116">必选`Property`过程定义是匹配的开始[Get 语句](get-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="90a56-117">如果执行时遇到`End Get`语句，控件返回到请求的属性值的语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="90a56-118">必选`If`...`Then`...`Else`块定义是匹配的开始`If`语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="90a56-119">请参阅[如果...然后...Else 语句](if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="90a56-120">终止开始是匹配的接口定义所需[Interface 语句](interface-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="90a56-121">模块定义开始是匹配的必选[Module 语句](module-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="90a56-122">必选命名空间定义是匹配的开始[Namespace 语句](namespace-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="90a56-123">运算符定义开始是匹配的必选[Operator Statement](operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="90a56-124">必选属性定义是匹配的开始[Property Statement](property-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="90a56-125">必选`RaiseEvent`访问器是匹配的开始`RaiseEvent`语句在自定义[Event 语句](event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="90a56-126">必选`RemoveHandler`访问器是匹配的开始`RemoveHandler`语句在自定义[Event 语句](event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="90a56-127">必选`Select`...`Case`块定义是匹配的开始`Select`语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="90a56-128">请参阅[选择...Case 语句](select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="90a56-129">必选`Property`过程定义是匹配的开始[Set 语句](set-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="90a56-130">如果执行时遇到`End Set`语句，控件返回到设置属性的值的语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="90a56-131">终止是匹配的开始的结构定义所需[Structure 语句](structure-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="90a56-132">必选`Sub`过程定义是匹配的开始[Sub 语句](sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="90a56-133">如果执行时遇到`End Sub`语句，控件返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="90a56-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="90a56-134">必选`SyncLock`块定义是匹配的开始`SyncLock`语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="90a56-135">请参阅[SyncLock 语句](synclock-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="90a56-136">必选`Try`...`Catch`...`Finally`块定义是匹配的开始`Try`语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="90a56-137">请参阅[尝试...Catch...Finally 语句](try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="90a56-138">必选`While`循环是匹配的开始定义`While`语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="90a56-139">请参阅[时...While 语句结束](while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="90a56-140">必选`With`块定义是匹配的开始`With`语句。</span><span class="sxs-lookup"><span data-stu-id="90a56-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="90a56-141">请参阅[使用...使用语句结束](with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="90a56-142">指令</span><span class="sxs-lookup"><span data-stu-id="90a56-142">Directives</span></span>

<span data-ttu-id="90a56-143">时前面加一个数字符号 (`#`)，则`End`关键字终止由相应的指令引入的预处理块。</span><span class="sxs-lookup"><span data-stu-id="90a56-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="90a56-144">部件</span><span class="sxs-lookup"><span data-stu-id="90a56-144">Part</span></span>|<span data-ttu-id="90a56-145">描述</span><span class="sxs-lookup"><span data-stu-id="90a56-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="90a56-146">必需。</span><span class="sxs-lookup"><span data-stu-id="90a56-146">Required.</span></span> <span data-ttu-id="90a56-147">终止预处理块的定义。</span><span class="sxs-lookup"><span data-stu-id="90a56-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="90a56-148">必选开始是匹配的一个外部源块[#ExternalSource 指令](../directives/externalsource-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="90a56-149">终止条件编译块开始是匹配的所需`#If`指令。</span><span class="sxs-lookup"><span data-stu-id="90a56-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="90a56-150">请参阅[#If......#Else 指令](../directives/if-then-else-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="90a56-151">必选开始是匹配的源区域块[#Region 指令](../directives/region-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="90a56-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="90a56-152">备注</span><span class="sxs-lookup"><span data-stu-id="90a56-152">Remarks</span></span>

<span data-ttu-id="90a56-153">[End 语句](end-statement.md)，而无需其他的关键字，将立即终止执行。</span><span class="sxs-lookup"><span data-stu-id="90a56-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="90a56-154">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="90a56-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="90a56-155">`End`不支持语句，而无需其他关键字。</span><span class="sxs-lookup"><span data-stu-id="90a56-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a56-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="90a56-156">See also</span></span>

- [<span data-ttu-id="90a56-157">End 语句</span><span class="sxs-lookup"><span data-stu-id="90a56-157">End Statement</span></span>](end-statement.md)
