---
title: 启用 JIT 附加调试
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
ms.openlocfilehash: 7adf1316a36d781439d364746fa11795a7fe165a
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217534"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="fb963-102">启用 JIT 附加调试</span><span class="sxs-lookup"><span data-stu-id="fb963-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="fb963-103">JIT 附加调试是用于描述如何在发生错误时将调试器附加到进程的词组，它也可以由特定的方法或函数触发。</span><span class="sxs-lookup"><span data-stu-id="fb963-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="fb963-104">JIT 附加调试用于以下错误情况：</span><span class="sxs-lookup"><span data-stu-id="fb963-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="fb963-105">未经处理的异常（在本机代码和托管代码中）。</span><span class="sxs-lookup"><span data-stu-id="fb963-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="fb963-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> 方法或 [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) 函数（Windows 7 系列）。</span><span class="sxs-lookup"><span data-stu-id="fb963-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="fb963-107">运行时灾难性错误。</span><span class="sxs-lookup"><span data-stu-id="fb963-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="fb963-108">也可通过调用以下方法和函数来触发 JIT 附加调试：</span><span class="sxs-lookup"><span data-stu-id="fb963-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="fb963-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fb963-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="fb963-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fb963-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="fb963-111">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) 函数 (Win32)。</span><span class="sxs-lookup"><span data-stu-id="fb963-111">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="fb963-112">在 .NET Framework 4 之前，.NET Framework 提供了单独的注册表项来控制本机调试器和托管调试器的行为。</span><span class="sxs-lookup"><span data-stu-id="fb963-112">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="fb963-113">从 .NET Framework 4 开始，将控件合并到一个注册表项下： HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug。</span><span class="sxs-lookup"><span data-stu-id="fb963-113">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="fb963-114">用户可为该注册表项设置值来确定是否调用调试器，如果调用，则确定是否使用需用户交互的对话框来调用。</span><span class="sxs-lookup"><span data-stu-id="fb963-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="fb963-115">有关设置此注册表项的信息，请参阅[配置自动调试](/windows/win32/debug/configuring-automatic-debugging)。</span><span class="sxs-lookup"><span data-stu-id="fb963-115">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb963-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb963-116">See also</span></span>

- [<span data-ttu-id="fb963-117">调试、跟踪和分析</span><span class="sxs-lookup"><span data-stu-id="fb963-117">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="fb963-118">使映像更易于调试</span><span class="sxs-lookup"><span data-stu-id="fb963-118">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
