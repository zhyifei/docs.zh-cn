---
title: "与非托管代码交互操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2db5b8c2425637e24086f54e8ef69b0e5aac3633
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="9bab3-102">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="9bab3-102">Interoperating with Unmanaged Code</span></span>
<span data-ttu-id="9bab3-103">.NET Framework 提升与 COM 组件、COM+ 服务、外部类型库和许多操作系统服务的交互。</span><span class="sxs-lookup"><span data-stu-id="9bab3-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="9bab3-104">托管和非托管对象模型之间的数据类型、方法签名和错误处理机制有所不同。</span><span class="sxs-lookup"><span data-stu-id="9bab3-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="9bab3-105">要简化 .NET Framework 组件和非托管代码之间的互操作并简化迁移路径，公共语言运行时需对客户端和服务器隐藏这些对象模型中的差异。</span><span class="sxs-lookup"><span data-stu-id="9bab3-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>  
  
 <span data-ttu-id="9bab3-106">在运行时控制下执行的代码称为托管代码。</span><span class="sxs-lookup"><span data-stu-id="9bab3-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="9bab3-107">反之，在运行时以外运行的代码称为非托管代码。</span><span class="sxs-lookup"><span data-stu-id="9bab3-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="9bab3-108">COM 组件、ActiveX 接口和 Win32 API 函数都是非托管代码的示例。</span><span class="sxs-lookup"><span data-stu-id="9bab3-108">COM components, ActiveX interfaces, and Win32 API functions are examples of unmanaged code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9bab3-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="9bab3-109">In This Section</span></span>  
 [<span data-ttu-id="9bab3-110">与非托管代码交互操作帮助主题</span><span class="sxs-lookup"><span data-stu-id="9bab3-110">Interoperating with Unmanaged Code How-to Topics</span></span>](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 <span data-ttu-id="9bab3-111">提供了与非托管代码交互操作相关的概念性文档中的所有帮助主题的链接。</span><span class="sxs-lookup"><span data-stu-id="9bab3-111">Provides links to all How-to topics found in the conceptual documentation for interoperating with unmanaged code.</span></span>  
  
 [<span data-ttu-id="9bab3-112">向 .NET Framework 公开 COM 组件</span><span class="sxs-lookup"><span data-stu-id="9bab3-112">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="9bab3-113">描述如何使用 .NET Framework 应用程序的 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="9bab3-113">Describes how to use COM components from .NET Framework applications.</span></span>  
  
 [<span data-ttu-id="9bab3-114">向 COM 公开 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="9bab3-114">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="9bab3-115">描述如何使用 COM 应用程序的 .NET Framework 组件。</span><span class="sxs-lookup"><span data-stu-id="9bab3-115">Describes how to use .NET Framework components from COM applications.</span></span>  
  
 [<span data-ttu-id="9bab3-116">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="9bab3-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="9bab3-117">描述如何使用平台调用调用非托管 DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="9bab3-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="9bab3-118">互操作的设计注意事项</span><span class="sxs-lookup"><span data-stu-id="9bab3-118">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 <span data-ttu-id="9bab3-119">提供有关编写集成 COM 组件的提示。</span><span class="sxs-lookup"><span data-stu-id="9bab3-119">Provides tips for writing integrated COM components.</span></span>  
  
 [<span data-ttu-id="9bab3-120">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="9bab3-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 <span data-ttu-id="9bab3-121">描述 COM 互操作和平台调用的封送处理。</span><span class="sxs-lookup"><span data-stu-id="9bab3-121">Describes marshaling for COM interop and platform invoke.</span></span>  
  
 [<span data-ttu-id="9bab3-122">如何：映射 HRESULT 和异常</span><span class="sxs-lookup"><span data-stu-id="9bab3-122">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 <span data-ttu-id="9bab3-123">描述异常和 HRESULT 之间的映射。</span><span class="sxs-lookup"><span data-stu-id="9bab3-123">Describes the mapping between exceptions and HRESULTs.</span></span>  
  
 [<span data-ttu-id="9bab3-124">使用泛型类型进行交互操作</span><span class="sxs-lookup"><span data-stu-id="9bab3-124">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 <span data-ttu-id="9bab3-125">描述用于 COM 互操作时的泛型类型行为。</span><span class="sxs-lookup"><span data-stu-id="9bab3-125">Describes the behavior of generic types when used in COM interop.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9bab3-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="9bab3-126">Related Sections</span></span>  
 [<span data-ttu-id="9bab3-127">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="9bab3-127">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="9bab3-128">提供一些链接，指向关于将 COM 组件并入 .NET Framework 应用程序中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9bab3-128">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>
