---
title: 事件和回调
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: KrzysztofCwalina
ms.openlocfilehash: c9ed52c5a313676baeba66f5cb79c7a56927babb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154419"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="d14e6-102">事件和回调</span><span class="sxs-lookup"><span data-stu-id="d14e6-102">Events and Callbacks</span></span>
<span data-ttu-id="d14e6-103">回调允许框架通过委托回调用户代码来实现可扩展性。</span><span class="sxs-lookup"><span data-stu-id="d14e6-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="d14e6-104">这些委托通常通过方法的参数传递给框架。</span><span class="sxs-lookup"><span data-stu-id="d14e6-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="d14e6-105">事件是一种特殊的回调的情况提供委托 （事件处理程序） 支持便捷且一致的语法。</span><span class="sxs-lookup"><span data-stu-id="d14e6-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="d14e6-106">此外，Visual Studio 的语句完成和设计人员提供的帮助中使用基于事件的 Api。</span><span class="sxs-lookup"><span data-stu-id="d14e6-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="d14e6-107">(请参阅[事件设计](../../../docs/standard/design-guidelines/event.md)。)</span><span class="sxs-lookup"><span data-stu-id="d14e6-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="d14e6-108">**✓ CONSIDER** 使用回调，以允许用户提供自定义代码来执行的框架。</span><span class="sxs-lookup"><span data-stu-id="d14e6-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="d14e6-109">**✓ CONSIDER** 使用事件以允许用户自定义一个框架，而无需了解面向对象的设计的行为。</span><span class="sxs-lookup"><span data-stu-id="d14e6-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="d14e6-110">**✓ DO** 更愿意使用事件而纯回调，因为它们是广泛的开发人员更熟悉，与 Visual Studio 语句完成集成。</span><span class="sxs-lookup"><span data-stu-id="d14e6-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="d14e6-111">**X AVOID** 性能敏感的 Api 中使用回调。</span><span class="sxs-lookup"><span data-stu-id="d14e6-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="d14e6-112">**✓ DO** 使用新`Func<...>`， `Action<...>`，或`Expression<...>`而不是定义回调的 Api 时的自定义委托的类型。</span><span class="sxs-lookup"><span data-stu-id="d14e6-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="d14e6-113">`Func<...>` 和`Action<...>`表示泛型委托。</span><span class="sxs-lookup"><span data-stu-id="d14e6-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="d14e6-114">`Expression<...>` 表示函数定义，可以编译并随后还调用在运行时，但可进行序列化和传递到远程进程。</span><span class="sxs-lookup"><span data-stu-id="d14e6-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="d14e6-115">**✓ DO** 测量和了解使用性能影响的`Expression<...>`，而不是使用`Func<...>`和`Action<...>`委托。</span><span class="sxs-lookup"><span data-stu-id="d14e6-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="d14e6-116">`Expression<...>` 类型是在逻辑上等同于大多数情况下`Func<...>`和`Action<...>`委托。</span><span class="sxs-lookup"><span data-stu-id="d14e6-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="d14e6-117">主要区别是，委托应将用于的本地进程方案;表达式适用于的情况下十分有益和无法计算表达式中的远程进程或计算机。</span><span class="sxs-lookup"><span data-stu-id="d14e6-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="d14e6-118">**✓ DO** 了解，通过调用委托，正在执行任意代码，且无法具有安全、 正确性和兼容性影响。</span><span class="sxs-lookup"><span data-stu-id="d14e6-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="d14e6-119">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="d14e6-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d14e6-120">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="d14e6-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14e6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d14e6-121">See also</span></span>

- [<span data-ttu-id="d14e6-122">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="d14e6-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="d14e6-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="d14e6-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
