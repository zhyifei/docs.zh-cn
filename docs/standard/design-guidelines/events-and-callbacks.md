---
title: 事件和回调
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90cc40024de627f151a4d0df879a65e5900004b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573628"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="ffe64-102">事件和回调</span><span class="sxs-lookup"><span data-stu-id="ffe64-102">Events and Callbacks</span></span>
<span data-ttu-id="ffe64-103">回调是允许回调到通过委托的用户代码的框架的扩展点。</span><span class="sxs-lookup"><span data-stu-id="ffe64-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="ffe64-104">这些委托通常通过方法的参数传递到框架。</span><span class="sxs-lookup"><span data-stu-id="ffe64-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="ffe64-105">事件是一种特殊的回调情况提供委托 （事件处理程序） 支持方便且一致的语法。</span><span class="sxs-lookup"><span data-stu-id="ffe64-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="ffe64-106">此外，Visual Studio 的语句完成和设计器提供在使用基于事件的 Api 的帮助。</span><span class="sxs-lookup"><span data-stu-id="ffe64-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="ffe64-107">(请参阅[事件设计](../../../docs/standard/design-guidelines/event.md)。)</span><span class="sxs-lookup"><span data-stu-id="ffe64-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="ffe64-108">**✓ CONSIDER**使用回调，以允许用户提供自定义代码来执行的框架。</span><span class="sxs-lookup"><span data-stu-id="ffe64-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="ffe64-109">**✓ CONSIDER**使用事件以允许用户自定义一个框架，而无需了解面向对象的设计的行为。</span><span class="sxs-lookup"><span data-stu-id="ffe64-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="ffe64-110">**✓ DO**更愿意使用事件而纯回调，因为它们是广泛的开发人员更熟悉，与 Visual Studio 语句完成集成。</span><span class="sxs-lookup"><span data-stu-id="ffe64-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="ffe64-111">**X AVOID**性能敏感的 Api 中使用回调。</span><span class="sxs-lookup"><span data-stu-id="ffe64-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="ffe64-112">**✓ DO**使用新`Func<...>`， `Action<...>`，或`Expression<...>`而不是定义回调的 Api 时的自定义委托的类型。</span><span class="sxs-lookup"><span data-stu-id="ffe64-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="ffe64-113">`Func<...>` 和`Action<...>`表示泛型委托。</span><span class="sxs-lookup"><span data-stu-id="ffe64-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="ffe64-114">`Expression<...>` 表示函数定义，可以编译并随后在运行时调用但是也可序列化和传递到远程进程。</span><span class="sxs-lookup"><span data-stu-id="ffe64-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="ffe64-115">**✓ DO**测量和了解使用性能影响的`Expression<...>`，而不是使用`Func<...>`和`Action<...>`委托。</span><span class="sxs-lookup"><span data-stu-id="ffe64-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="ffe64-116">`Expression<...>` 类型是在逻辑上等效于大多数情况下`Func<...>`和`Action<...>`委托。</span><span class="sxs-lookup"><span data-stu-id="ffe64-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="ffe64-117">它们之间的主要区别是委托旨在用于本地进程方案;表达式用于其中是有益的和可能在远程进程或计算机中的表达式进行求值的情况。</span><span class="sxs-lookup"><span data-stu-id="ffe64-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="ffe64-118">**✓ DO**了解，通过调用委托，正在执行任意代码，且无法具有安全、 正确性和兼容性影响。</span><span class="sxs-lookup"><span data-stu-id="ffe64-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="ffe64-119">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="ffe64-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ffe64-120">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="ffe64-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe64-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffe64-121">See Also</span></span>  
 [<span data-ttu-id="ffe64-122">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="ffe64-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="ffe64-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="ffe64-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
