---
title: 异常互操作性
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794620"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="59583-102">在非托管代码中处理互操作异常</span><span class="sxs-lookup"><span data-stu-id="59583-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="59583-103">仅在 Windows 平台上支持非托管代码异常互操作。</span><span class="sxs-lookup"><span data-stu-id="59583-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="59583-104">非 Windows 平台上会出现可移植性问题。</span><span class="sxs-lookup"><span data-stu-id="59583-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="59583-105">由于 Unix ABI 没有异常处理的定义，因此托管代码无法知道异常机制的内部工作方式。</span><span class="sxs-lookup"><span data-stu-id="59583-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="59583-106">因此，异常最终可能导致不可预知的行为和故障。</span><span class="sxs-lookup"><span data-stu-id="59583-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="59583-107">Setjmp/Longjmp 行为</span><span class="sxs-lookup"><span data-stu-id="59583-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="59583-108">不支持与 `setjmp` 和 `longjmp` C 函数的互操作。</span><span class="sxs-lookup"><span data-stu-id="59583-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="59583-109">无法使用 `longjmp` 跳过托管帧。</span><span class="sxs-lookup"><span data-stu-id="59583-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="59583-110">有关详细信息，请参阅 [longjmp 文档](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp)。</span><span class="sxs-lookup"><span data-stu-id="59583-110">For more information, see [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="59583-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="59583-111">See also</span></span>

- [<span data-ttu-id="59583-112">异常</span><span class="sxs-lookup"><span data-stu-id="59583-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="59583-113">与本机库的互操作</span><span class="sxs-lookup"><span data-stu-id="59583-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
