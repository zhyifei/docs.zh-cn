---
title: nonComVisibleBaseClass MDA
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb0810a9e0ffce825abecc87eb2698920209d86f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171803"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="4a15f-102">nonComVisibleBaseClass MDA</span><span class="sxs-lookup"><span data-stu-id="4a15f-102">nonComVisibleBaseClass MDA</span></span>
<span data-ttu-id="4a15f-103">当本机或非托管代码在派生自非 COM 可见基类的 COM 可见托管类的 COM 可调用包装器 (CCW) 调用 `QueryInterface` 时，将激活 `nonComVisibleBaseClass` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="4a15f-103">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="4a15f-104">仅在调用需要 COM 可见托管类的类接口或默认 `IDispatch` 的情况下，`QueryInterface` 调用才会引起 MDA 激活。</span><span class="sxs-lookup"><span data-stu-id="4a15f-104">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="4a15f-105">对应用了 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 特性的显式接口调用 `QueryInterface`，并且调用由 COM 可见类显式实现时，则不会激活 MDA。</span><span class="sxs-lookup"><span data-stu-id="4a15f-105">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4a15f-106">症状</span><span class="sxs-lookup"><span data-stu-id="4a15f-106">Symptoms</span></span>  
 <span data-ttu-id="4a15f-107">本机代码发起的`QueryInterface` 调用失败并返回 COR_E_INVALIDOPERATION HRESULT。</span><span class="sxs-lookup"><span data-stu-id="4a15f-107">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="4a15f-108">HRESULT 可能因运行时禁止可能激活此 MDA 的 `QueryInterface` 调用。</span><span class="sxs-lookup"><span data-stu-id="4a15f-108">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4a15f-109">原因</span><span class="sxs-lookup"><span data-stu-id="4a15f-109">Cause</span></span>  
 <span data-ttu-id="4a15f-110">运行时不允许派生自非 COM 可见类的 COM 可见类的类接口或默认 `IDispatch` 接口调用 `QueryInterface`，因为可能引发版本控制问题。</span><span class="sxs-lookup"><span data-stu-id="4a15f-110">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="4a15f-111">例如，如果向非 COM 可见基类添加任何公共成员，则使用派生类的现有 COM 客户端可能会中止，因为进行此类更改时，包含基类成员的派生类的 vtable 可能被更改。</span><span class="sxs-lookup"><span data-stu-id="4a15f-111">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="4a15f-112">向 COM 公开的显式接口没有这个问题，因为它们不将接口的基成员包括到 vtable 中。</span><span class="sxs-lookup"><span data-stu-id="4a15f-112">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4a15f-113">解决方法</span><span class="sxs-lookup"><span data-stu-id="4a15f-113">Resolution</span></span>  
 <span data-ttu-id="4a15f-114">不要公开类接口。</span><span class="sxs-lookup"><span data-stu-id="4a15f-114">Do not expose the class interface.</span></span> <span data-ttu-id="4a15f-115">定义显式接口并向其应用 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="4a15f-115">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4a15f-116">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="4a15f-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="4a15f-117">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="4a15f-117">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4a15f-118">Output</span><span class="sxs-lookup"><span data-stu-id="4a15f-118">Output</span></span>  
 <span data-ttu-id="4a15f-119">下面是有关在派生自非 COM 可见类 `Base` 的 COM 可见类 `Derived` 上调用 `QueryInterface` 的示例消息。</span><span class="sxs-lookup"><span data-stu-id="4a15f-119">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```  
A QueryInterface call was made requesting the class interface of COM   
visible managed class 'Derived'. However since this class derives from   
non COM visible class 'Base', the QueryInterface call will fail. This   
is done to prevent the non COM visible base class from being   
constrained by the COM versioning rules.   
```  
  
## <a name="configuration"></a><span data-ttu-id="4a15f-120">配置</span><span class="sxs-lookup"><span data-stu-id="4a15f-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a15f-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a15f-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4a15f-122">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="4a15f-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4a15f-123">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="4a15f-123">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
