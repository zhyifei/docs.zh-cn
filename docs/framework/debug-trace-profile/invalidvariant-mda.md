---
title: invalidVariant MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64f5a4425d70974bae8c4f7bec28041e687fe95f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228479"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="b4dfc-102">invalidVariant MDA</span><span class="sxs-lookup"><span data-stu-id="b4dfc-102">invalidVariant MDA</span></span>
<span data-ttu-id="b4dfc-103">在从本机或非托管代码到托管代码的调用期间，如果遇到无效的 `VARIANT` 结构，将激活 `invalidVariant` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b4dfc-104">症状</span><span class="sxs-lookup"><span data-stu-id="b4dfc-104">Symptoms</span></span>  
 <span data-ttu-id="b4dfc-105">在本机和托管代码之间转换的过程中的意外行为涉及将 `VARIANT` 封送处理到对象。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b4dfc-106">原因</span><span class="sxs-lookup"><span data-stu-id="b4dfc-106">Cause</span></span>  
 <span data-ttu-id="b4dfc-107">本机代码正在向托管代码传递格式不正确的 `VARIANT` 结构。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="b4dfc-108">如果 `VARIANT` 无效，运行时则会尝试向某个对象封送 `VARIANT` 并激活 MDA。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="b4dfc-109">无效 `VARIANT` 的示例包括具有 `VARTYPE` VT_EMPTY &#124; VT_BYREF 的 `VARIANT` 或具有 `VARTYPE` VT_VARIANT 的 `VARIANT`。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b4dfc-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="b4dfc-110">Resolution</span></span>  
 <span data-ttu-id="b4dfc-111">传递 `VARIANT` 的本机或非托管代码必须确保 `VARIANT` 格式正确且已初始化。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b4dfc-112">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="b4dfc-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="b4dfc-113">此 MDA 对运行时无任何影响。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b4dfc-114">Output</span><span class="sxs-lookup"><span data-stu-id="b4dfc-114">Output</span></span>  
 <span data-ttu-id="b4dfc-115">MDA 消息指示运行时检测到由非托管模块传递给托管代码的无效 `VARIANT`。</span><span class="sxs-lookup"><span data-stu-id="b4dfc-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b4dfc-116">配置</span><span class="sxs-lookup"><span data-stu-id="b4dfc-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4dfc-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4dfc-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b4dfc-118">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="b4dfc-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b4dfc-119">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="b4dfc-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
