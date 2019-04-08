---
title: invalidMemberDeclaration MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e5b4cb4a04a79a748f4ea2292bac67a88a6e9f8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131282"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="dd293-102">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="dd293-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="dd293-103">激活 `invalidMemberDeclaration` 托管调试助手 (MDA) 以报告在确定如何封送要从 COM 调用的成员的参数期间发生的错误。</span><span class="sxs-lookup"><span data-stu-id="dd293-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="dd293-104">症状</span><span class="sxs-lookup"><span data-stu-id="dd293-104">Symptoms</span></span>  
 <span data-ttu-id="dd293-105">一个失败 HRESULT 被返回到 COM，且未调用托管方法。</span><span class="sxs-lookup"><span data-stu-id="dd293-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="dd293-106">原因</span><span class="sxs-lookup"><span data-stu-id="dd293-106">Cause</span></span>  
 <span data-ttu-id="dd293-107">这很有可能是因为不兼容其中一个参数上的 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="dd293-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="dd293-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="dd293-108">Resolution</span></span>  
 <span data-ttu-id="dd293-109">指定参数上的有效 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="dd293-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="dd293-110">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="dd293-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="dd293-111">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="dd293-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="dd293-112">Output</span><span class="sxs-lookup"><span data-stu-id="dd293-112">Output</span></span>  
 <span data-ttu-id="dd293-113">信息性消息包括成员名称、类型名称和错误消息。</span><span class="sxs-lookup"><span data-stu-id="dd293-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="dd293-114">配置</span><span class="sxs-lookup"><span data-stu-id="dd293-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd293-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd293-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="dd293-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="dd293-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="dd293-117">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="dd293-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
