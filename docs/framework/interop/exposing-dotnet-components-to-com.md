---
title: "向 COM 公开 .NET Framework 组件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1bba04ed410eb195869d2a4bc2868872b04c0d0
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="exposing-net-framework-components-to-com"></a><span data-ttu-id="1121d-102">向 COM 公开 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="1121d-102">Exposing .NET Framework Components to COM</span></span>
<span data-ttu-id="1121d-103">对开发人员而言，编写 .NET 类型以及从非托管代码使用该类型是不同的活动。</span><span class="sxs-lookup"><span data-stu-id="1121d-103">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="1121d-104">本部分介绍编写与 COM 客户端互操作的托管代码的几个提示：</span><span class="sxs-lookup"><span data-stu-id="1121d-104">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>  
  
-   <span data-ttu-id="1121d-105">[为互操作限定 .NET 类型](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="1121d-105">[Qualifying .NET types for interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).</span></span>  
  
     <span data-ttu-id="1121d-106">要向 COM 公开的所有托管类型、方法、属性、字段和事件都必须是公开的。</span><span class="sxs-lookup"><span data-stu-id="1121d-106">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="1121d-107">各类型必须具有公共默认构造函数，通过 COM 只能调用该构造函数。</span><span class="sxs-lookup"><span data-stu-id="1121d-107">Types must have a public default constructor, which is the only constructor that can be invoked through COM.</span></span>  
  
-   <span data-ttu-id="1121d-108">[应用互操作属性](../../../docs/framework/interop/applying-interop-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="1121d-108">[Applying interop attributes](../../../docs/framework/interop/applying-interop-attributes.md).</span></span>  
  
     <span data-ttu-id="1121d-109">托管代码中的自定义属性可增强组件的互操作性。</span><span class="sxs-lookup"><span data-stu-id="1121d-109">Custom attributes within managed code can enhance the interoperability of a component.</span></span>  
  
-   <span data-ttu-id="1121d-110">[将 COM 的程序集打包](../../../docs/framework/interop/packaging-an-assembly-for-com.md)。</span><span class="sxs-lookup"><span data-stu-id="1121d-110">[Packaging an assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span></span>  
  
     <span data-ttu-id="1121d-111">COM 开发人员可能会要求用户总结引用和部署程序集所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="1121d-111">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>  
  
 <span data-ttu-id="1121d-112">此外，本部分还确定了从 COM 客户端使用托管类型的相关任务。</span><span class="sxs-lookup"><span data-stu-id="1121d-112">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>  
  
#### <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="1121d-113">从 COM 使用托管类型</span><span class="sxs-lookup"><span data-stu-id="1121d-113">To consume a managed type from COM</span></span>  
  
1.  <span data-ttu-id="1121d-114">[向 COM 注册程序集](../../../docs/framework/interop/registering-assemblies-with-com.md)。</span><span class="sxs-lookup"><span data-stu-id="1121d-114">[Register assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md).</span></span>  
  
     <span data-ttu-id="1121d-115">必须在设计时注册程序集（和类型库）中的类型。</span><span class="sxs-lookup"><span data-stu-id="1121d-115">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="1121d-116">如果安装程序未注册程序集，请指示 COM 开发人员使用 Regasm.exe。</span><span class="sxs-lookup"><span data-stu-id="1121d-116">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>  
  
2.  <span data-ttu-id="1121d-117">[从 COM 引用 .NET 类型](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)。</span><span class="sxs-lookup"><span data-stu-id="1121d-117">[Reference .NET types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).</span></span>  
  
     <span data-ttu-id="1121d-118">COM 开发人员可使用当前使用的相同工具和技术引用程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="1121d-118">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>  
  
3.  <span data-ttu-id="1121d-119">[调用 .NET 对象](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="1121d-119">[Call a .NET object](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100)).</span></span>  
  
     <span data-ttu-id="1121d-120">COM 开发人员可采用在任何非托管类型上调用方法的方式在 .NET 对象上调用方法。</span><span class="sxs-lookup"><span data-stu-id="1121d-120">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="1121d-121">例如，COM CoCreateInstance API 激活 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="1121d-121">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>  
  
4.  <span data-ttu-id="1121d-122">[为 COM 访问部署应用程序](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="1121d-122">[Deploy an application for COM access](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100)).</span></span>  
  
     <span data-ttu-id="1121d-123">具有强名称的程序集可安装在全局程序集缓存中，并向其发布者请求签名。</span><span class="sxs-lookup"><span data-stu-id="1121d-123">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="1121d-124">不具有强名称的程序集必须安装在客户端的应用程序目录中。</span><span class="sxs-lookup"><span data-stu-id="1121d-124">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1121d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1121d-125">See Also</span></span>  
 [<span data-ttu-id="1121d-126">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="1121d-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="1121d-127">COM 互操作示例：COM 客户端和 .NET 服务器</span><span class="sxs-lookup"><span data-stu-id="1121d-127">COM Interop Sample: COM Client and .NET Server</span></span>](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
