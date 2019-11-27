---
title: End <keyword> 语句
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343739"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="621ce-102">End \<关键字 > 语句（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="621ce-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="621ce-103">后跟附加的关键字时，将终止该关键字引入的语句块的定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="621ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="621ce-104">Syntax</span></span>

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
  
## <a name="parts"></a><span data-ttu-id="621ce-105">部件</span><span class="sxs-lookup"><span data-stu-id="621ce-105">Parts</span></span>

|<span data-ttu-id="621ce-106">部件</span><span class="sxs-lookup"><span data-stu-id="621ce-106">Part</span></span>|<span data-ttu-id="621ce-107">说明</span><span class="sxs-lookup"><span data-stu-id="621ce-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="621ce-108">必需。</span><span class="sxs-lookup"><span data-stu-id="621ce-108">Required.</span></span> <span data-ttu-id="621ce-109">终止编程元素的定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="621ce-110">需要终止自定义[事件语句](event-statement.md)中的匹配 `AddHandler` 语句开始的 `AddHandler` 访问器。</span><span class="sxs-lookup"><span data-stu-id="621ce-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="621ce-111">需要终止由匹配的[类语句](class-statement.md)开始的类定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="621ce-112">需要终止由匹配[枚举语句](enum-statement.md)开始的枚举定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="621ce-113">需要终止匹配[事件语句](event-statement.md)开始的 `Custom` 事件定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="621ce-114">需要终止由匹配[函数语句](function-statement.md)开始的 `Function` 过程定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="621ce-115">如果执行过程中遇到 `End Function` 语句，则控件会返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="621ce-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="621ce-116">需要终止由匹配的[Get 语句](get-statement.md)开始的 `Property` 过程定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="621ce-117">如果执行遇到 `End Get` 语句，控制将返回到请求属性值的语句。</span><span class="sxs-lookup"><span data-stu-id="621ce-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="621ce-118">需要终止 `If`...`Then`...`Else` 按匹配的 `If` 语句开始的块定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="621ce-119">请参阅[If .。。Then .。。Else 语句](if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="621ce-120">需要终止由匹配的[Interface 语句](interface-statement.md)开始的接口定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="621ce-121">需要终止匹配[Module 语句](module-statement.md)开始的模块定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="621ce-122">需要终止由匹配的[命名空间语句](namespace-statement.md)开始的命名空间定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="621ce-123">需要终止由匹配的[Operator 语句](operator-statement.md)开始的运算符定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="621ce-124">需要终止由匹配的[属性语句](property-statement.md)开始的属性定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="621ce-125">需要终止自定义[事件语句](event-statement.md)中的匹配 `RaiseEvent` 语句开始的 `RaiseEvent` 访问器。</span><span class="sxs-lookup"><span data-stu-id="621ce-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="621ce-126">需要终止自定义[事件语句](event-statement.md)中的匹配 `RemoveHandler` 语句开始的 `RemoveHandler` 访问器。</span><span class="sxs-lookup"><span data-stu-id="621ce-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="621ce-127">需要终止 `Select`...`Case` 块定义由匹配的 `Select` 语句开始。</span><span class="sxs-lookup"><span data-stu-id="621ce-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="621ce-128">请参阅[Select .。。Case 语句](select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="621ce-129">需要终止由匹配[Set 语句](set-statement.md)开始的 `Property` 过程定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="621ce-130">如果执行遇到 `End Set` 语句，控制将返回到设置属性值的语句。</span><span class="sxs-lookup"><span data-stu-id="621ce-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="621ce-131">需要终止由匹配的[结构语句](structure-statement.md)开始的结构定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="621ce-132">需要终止由匹配的[Sub 语句](sub-statement.md)开始的 `Sub` 过程定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="621ce-133">如果执行过程中遇到 `End Sub` 语句，则控件会返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="621ce-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="621ce-134">需要终止由匹配的 `SyncLock` 语句开始的 `SyncLock` 块定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="621ce-135">请参阅[SyncLock 语句](synclock-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="621ce-136">需要终止 `Try`...`Catch`...`Finally` 按匹配的 `Try` 语句开始的块定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="621ce-137">请参阅[Try .。。Catch .。。Finally 语句](try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="621ce-138">需要终止由匹配的 `While` 语句开始的 `While` 循环定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="621ce-139">查看[.。。End While 语句](while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="621ce-140">需要终止由匹配的 `With` 语句开始的 `With` 块定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="621ce-141">查看[方式 .。。End With 语句](with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="621ce-142">指令</span><span class="sxs-lookup"><span data-stu-id="621ce-142">Directives</span></span>

<span data-ttu-id="621ce-143">如果前面有一个数字符号（`#`），则 `End` 关键字将终止相应指令引入的预处理块。</span><span class="sxs-lookup"><span data-stu-id="621ce-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="621ce-144">部件</span><span class="sxs-lookup"><span data-stu-id="621ce-144">Part</span></span>|<span data-ttu-id="621ce-145">说明</span><span class="sxs-lookup"><span data-stu-id="621ce-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="621ce-146">必需。</span><span class="sxs-lookup"><span data-stu-id="621ce-146">Required.</span></span> <span data-ttu-id="621ce-147">终止预处理块的定义。</span><span class="sxs-lookup"><span data-stu-id="621ce-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="621ce-148">需要终止由匹配的[#ExternalSource 指令](../directives/externalsource-directive.md)开始的外部源块。</span><span class="sxs-lookup"><span data-stu-id="621ce-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="621ce-149">需要终止由匹配的 `#If` 指令开始的条件编译块。</span><span class="sxs-lookup"><span data-stu-id="621ce-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="621ce-150">请参阅[#If .。。Then ... #Else 指令](../directives/if-then-else-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="621ce-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="621ce-151">需要终止由匹配的[#Region 指令](../directives/region-directive.md)开始的源区域块。</span><span class="sxs-lookup"><span data-stu-id="621ce-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="621ce-152">备注</span><span class="sxs-lookup"><span data-stu-id="621ce-152">Remarks</span></span>

<span data-ttu-id="621ce-153">[End 语句](end-statement.md)没有其他关键字，则立即终止执行。</span><span class="sxs-lookup"><span data-stu-id="621ce-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="621ce-154">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="621ce-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="621ce-155">不支持不带额外关键字的 `End` 语句。</span><span class="sxs-lookup"><span data-stu-id="621ce-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621ce-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="621ce-156">See also</span></span>

- [<span data-ttu-id="621ce-157">End 语句</span><span class="sxs-lookup"><span data-stu-id="621ce-157">End Statement</span></span>](end-statement.md)
