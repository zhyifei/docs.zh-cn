---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135616"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a><span data-ttu-id="9ce6c-101">不支持处理损坏状态异常</span><span class="sxs-lookup"><span data-stu-id="9ce6c-101">Handling corrupted state exceptions is not supported</span></span>

<span data-ttu-id="9ce6c-102">不支持在 .NET Core 中处理损坏进程状态异常。</span><span class="sxs-lookup"><span data-stu-id="9ce6c-102">Handling corrupted-process-state exceptions in .NET Core is not supported.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9ce6c-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="9ce6c-103">Change description</span></span>

<span data-ttu-id="9ce6c-104">以前，损坏进程状态异常可以由托管代码异常处理程序进行捕获和处理，例如在 C# 中使用 [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="9ce6c-104">Previously, corrupted-process-state exceptions could be caught and handled by managed code exception handlers, for example, by using a [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) statement in C#.</span></span>

<span data-ttu-id="9ce6c-105">从 .NET Core 1.0 开始，损坏进程状态异常无法由托管代码进行处理。</span><span class="sxs-lookup"><span data-stu-id="9ce6c-105">Starting in .NET Core 1.0, corrupted-process-state exceptions cannot be handled by managed code.</span></span> <span data-ttu-id="9ce6c-106">公共语言运行时不会将损坏进程状态异常传递给托管代码。</span><span class="sxs-lookup"><span data-stu-id="9ce6c-106">The common language runtime doesn't deliver corrupted-process-state exceptions to managed code.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9ce6c-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="9ce6c-107">Version introduced</span></span>

<span data-ttu-id="9ce6c-108">1.0</span><span class="sxs-lookup"><span data-stu-id="9ce6c-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9ce6c-109">建议操作</span><span class="sxs-lookup"><span data-stu-id="9ce6c-109">Recommended action</span></span>

<span data-ttu-id="9ce6c-110">通过解决导致这些异常的情况来避免需要处理损坏进程状态异常。</span><span class="sxs-lookup"><span data-stu-id="9ce6c-110">Avoid the need to handle corrupted-process-state exceptions by addressing the situations that lead to them instead.</span></span> <span data-ttu-id="9ce6c-111">如果绝对有必要处理损坏进程状态异常，请在 C 或 C++ 代码中编写异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="9ce6c-111">If it's absolutely necessary to handle corrupted-process-state exceptions, write the exception handler in C or C++ code.</span></span>

#### <a name="category"></a><span data-ttu-id="9ce6c-112">类别</span><span class="sxs-lookup"><span data-stu-id="9ce6c-112">Category</span></span>

<span data-ttu-id="9ce6c-113">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="9ce6c-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9ce6c-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9ce6c-114">Affected APIs</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [<span data-ttu-id="9ce6c-115">legacyCorruptedStateExceptionsPolicy 元素</span><span class="sxs-lookup"><span data-stu-id="9ce6c-115">legacyCorruptedStateExceptionsPolicy element</span></span>](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
