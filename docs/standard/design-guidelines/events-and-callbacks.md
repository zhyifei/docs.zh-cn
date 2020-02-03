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
ms.openlocfilehash: 7dab759ba48104530fc41e46f6f2bba18d6c4456
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741653"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="d3ee9-102">事件和回调</span><span class="sxs-lookup"><span data-stu-id="d3ee9-102">Events and Callbacks</span></span>
<span data-ttu-id="d3ee9-103">回调允许框架通过委托回调用户代码来实现可扩展性。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="d3ee9-104">这些委托通常通过方法的参数传递给框架。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="d3ee9-105">事件是回调的一种特殊情况，它支持通过便捷且一致的语法来提供委托（事件处理程序）。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="d3ee9-106">此外，可以借助 Visual Studio 的语句完成和设计器功能来使用基于事件的 API。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="d3ee9-107">（请参阅[事件设计](../../../docs/standard/design-guidelines/event.md)。）</span><span class="sxs-lookup"><span data-stu-id="d3ee9-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>

 <span data-ttu-id="d3ee9-108">✔️考虑使用回调来允许用户提供要由框架执行的自定义代码。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-108">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="d3ee9-109">✔️考虑使用事件来允许用户自定义框架的行为，而无需了解面向对象的设计。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-109">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="d3ee9-110">✔️确实比普通回调更喜欢事件，因为它们对更广泛的开发人员更熟悉，并与 Visual Studio 语句完成集成。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-110">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="d3ee9-111">❌ 避免在性能敏感的 Api 中使用回调。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-111">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="d3ee9-112">在使用回调定义 Api 时，✔️会使用新的 `Func<...>`、`Action<...>`或 `Expression<...>` 类型而不是自定义委托。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-112">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="d3ee9-113">`Func<...>` 和 `Action<...>` 表示泛型委托。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="d3ee9-114">`Expression<...>` 表示可以编译并随后在运行时调用的函数定义，但也可以进行序列化并将其传递到远程进程。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="d3ee9-115">✔️使用 `Expression<...>`度量并了解性能影响，而不是使用 `Func<...>` 和 `Action<...>` 委托。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-115">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="d3ee9-116">在大多数情况下，`Expression<...>` 类型在逻辑上等同于 `Func<...>` 和 `Action<...>` 委托。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="d3ee9-117">它们之间的主要区别在于委托旨在用于本地处理方案;表达式适用于在远程进程或计算机中计算表达式的好处。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="d3ee9-118">✔️可以通过调用委托来了解这一点，因为你正在执行任意代码，这可能会对安全性、正确性和兼容性产生影响。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-118">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="d3ee9-119">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="d3ee9-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d3ee9-120">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="d3ee9-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d3ee9-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3ee9-121">See also</span></span>

- [<span data-ttu-id="d3ee9-122">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="d3ee9-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="d3ee9-123">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="d3ee9-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
