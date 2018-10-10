---
title: 使用标准异常类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ea4a61be3a76c30c564cbf98ba3318fc6c3e7d4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216090"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="a72fe-102">使用标准异常类型</span><span class="sxs-lookup"><span data-stu-id="a72fe-102">Using Standard Exception Types</span></span>
<span data-ttu-id="a72fe-103">本部分介绍 Framework 提供的标准异常及其用法的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a72fe-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="a72fe-104">该列表并非详尽无遗。</span><span class="sxs-lookup"><span data-stu-id="a72fe-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="a72fe-105">有关其他 Framework 异常类型的用法，请参阅 .NET Framework 参考文档。</span><span class="sxs-lookup"><span data-stu-id="a72fe-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="a72fe-106">Exception 和 SystemException</span><span class="sxs-lookup"><span data-stu-id="a72fe-106">Exception and SystemException</span></span>  
 <span data-ttu-id="a72fe-107">**X DO NOT** 引发<xref:System.Exception?displayProperty=nameWithType>或<xref:System.SystemException?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a72fe-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a72fe-108">**X DO NOT** 捕获`System.Exception`或`System.SystemException`在 framework 代码中，除非您想要重新引发。</span><span class="sxs-lookup"><span data-stu-id="a72fe-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="a72fe-109">**X AVOID** 捕捉`System.Exception`或`System.SystemException`，除非在顶级异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="a72fe-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="a72fe-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="a72fe-110">ApplicationException</span></span>  
 <span data-ttu-id="a72fe-111">**X DO NOT** 引发或从其派生<xref:System.ApplicationException>。</span><span class="sxs-lookup"><span data-stu-id="a72fe-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="a72fe-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="a72fe-112">InvalidOperationException</span></span>  
 <span data-ttu-id="a72fe-113">**✓ DO** 引发<xref:System.InvalidOperationException>如果此对象处于不合适的状态。</span><span class="sxs-lookup"><span data-stu-id="a72fe-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="a72fe-114">ArgumentException、ArgumentNullException 和 ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="a72fe-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="a72fe-115">**✓ DO** 引发<xref:System.ArgumentException>或如果错误的自变量传递给成员及其子类型之一。</span><span class="sxs-lookup"><span data-stu-id="a72fe-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="a72fe-116">如果适用，倾向于使用的派生程度最高的异常类型。</span><span class="sxs-lookup"><span data-stu-id="a72fe-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="a72fe-117">**✓ DO** 设置`ParamName`属性时引发的子类之一`ArgumentException`。</span><span class="sxs-lookup"><span data-stu-id="a72fe-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="a72fe-118">此属性表示引发异常的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="a72fe-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="a72fe-119">请注意，可以使用一个构造函数重载来设置该属性。</span><span class="sxs-lookup"><span data-stu-id="a72fe-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="a72fe-120">**✓ DO** 使用`value`属性 setter 的隐式值参数的名称。</span><span class="sxs-lookup"><span data-stu-id="a72fe-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="a72fe-121">NullReferenceException、IndexOutOfRangeException 和 AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="a72fe-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="a72fe-122">**X DO NOT** 允许公开可调用 Api 显式或隐式引发<xref:System.NullReferenceException>， <xref:System.AccessViolationException>，或<xref:System.IndexOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="a72fe-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="a72fe-123">这些例外情况是保留和引发的执行引擎和在大多数情况下指示 bug。</span><span class="sxs-lookup"><span data-stu-id="a72fe-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="a72fe-124">应检查参数以避免引发这些异常。</span><span class="sxs-lookup"><span data-stu-id="a72fe-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="a72fe-125">引发这些异常会暴露方法的实现细节，这些细节可能会随着时间而改变。</span><span class="sxs-lookup"><span data-stu-id="a72fe-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="a72fe-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="a72fe-126">StackOverflowException</span></span>  
 <span data-ttu-id="a72fe-127">**X DO NOT** 显式引发<xref:System.StackOverflowException>。</span><span class="sxs-lookup"><span data-stu-id="a72fe-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="a72fe-128">应仅由 CLR 显式引发异常。</span><span class="sxs-lookup"><span data-stu-id="a72fe-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="a72fe-129">**X DO NOT** 捕获`StackOverflowException`。</span><span class="sxs-lookup"><span data-stu-id="a72fe-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="a72fe-130">在存在任意堆栈溢出的情况下编写保持一致的托管代码几乎是不可能的。</span><span class="sxs-lookup"><span data-stu-id="a72fe-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="a72fe-131">通过使用探测功能将堆栈溢出移动到明确定义的位置而不是从任意堆栈溢出中退出，CLR 的非托管部分可以保持一致。</span><span class="sxs-lookup"><span data-stu-id="a72fe-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="a72fe-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="a72fe-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="a72fe-133">**X DO NOT** 显式引发<xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="a72fe-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="a72fe-134">将仅由 CLR 基础结构引发此异常。</span><span class="sxs-lookup"><span data-stu-id="a72fe-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="a72fe-135">ComException、SEHException 和 ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="a72fe-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="a72fe-136">**X DO NOT** 显式引发<xref:System.Runtime.InteropServices.COMException>， <xref:System.ExecutionEngineException>，和<xref:System.Runtime.InteropServices.SEHException>。</span><span class="sxs-lookup"><span data-stu-id="a72fe-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="a72fe-137">这些异常将仅由 CLR 基础结构引发。</span><span class="sxs-lookup"><span data-stu-id="a72fe-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="a72fe-138">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a72fe-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a72fe-139">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="a72fe-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72fe-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="a72fe-140">See also</span></span>

- [<span data-ttu-id="a72fe-141">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="a72fe-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="a72fe-142">异常的设计准则</span><span class="sxs-lookup"><span data-stu-id="a72fe-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
