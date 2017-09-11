---
title: invalidMemberDeclaration MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 34db255e3e04776123d30ad06dc3026c4e75addd
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="c545c-102">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="c545c-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="c545c-103">激活 `invalidMemberDeclaration` 托管调试助手 (MDA) 以报告在确定如何封送要从 COM 调用的成员的参数期间发生的错误。</span><span class="sxs-lookup"><span data-stu-id="c545c-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c545c-104">症状</span><span class="sxs-lookup"><span data-stu-id="c545c-104">Symptoms</span></span>  
 <span data-ttu-id="c545c-105">一个失败 HRESULT 被返回到 COM，且未调用托管方法。</span><span class="sxs-lookup"><span data-stu-id="c545c-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c545c-106">原因</span><span class="sxs-lookup"><span data-stu-id="c545c-106">Cause</span></span>  
 <span data-ttu-id="c545c-107">这很有可能是因为不兼容其中一个参数上的 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="c545c-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c545c-108">解决方法</span><span class="sxs-lookup"><span data-stu-id="c545c-108">Resolution</span></span>  
 <span data-ttu-id="c545c-109">指定参数上的有效 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="c545c-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c545c-110">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="c545c-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="c545c-111">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="c545c-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c545c-112">输出</span><span class="sxs-lookup"><span data-stu-id="c545c-112">Output</span></span>  
 <span data-ttu-id="c545c-113">信息性消息包括成员名称、类型名称和错误消息。</span><span class="sxs-lookup"><span data-stu-id="c545c-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c545c-114">配置</span><span class="sxs-lookup"><span data-stu-id="c545c-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c545c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c545c-115">See Also</span></span>  
 <span data-ttu-id="c545c-116"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="c545c-116"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
 <span data-ttu-id="c545c-117">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="c545c-117">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 [<span data-ttu-id="c545c-118">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="c545c-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

