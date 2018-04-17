---
title: 将 COM 的程序集打包
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c1e3ee38f98eae46c09ec2175f3c9af01288bd2
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="packaging-an-assembly-for-com"></a><span data-ttu-id="8c0cc-102">将 COM 的程序集打包</span><span class="sxs-lookup"><span data-stu-id="8c0cc-102">Packaging an Assembly for COM</span></span>
<span data-ttu-id="8c0cc-103">COM 开发人员可从其计划纳入应用程序的托管类型相关信息中受益：</span><span class="sxs-lookup"><span data-stu-id="8c0cc-103">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>  
  
-   <span data-ttu-id="8c0cc-104">COM 应用程序可使用的类型列表</span><span class="sxs-lookup"><span data-stu-id="8c0cc-104">A list of types that COM applications can consume</span></span>  
  
     <span data-ttu-id="8c0cc-105">某些托管类型对 COM 不可见；某些可见但不可创建；某些既可见又可创建。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-105">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="8c0cc-106">程序集可以包括不可见、可见、不可创建和可创建类型的任何组合。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-106">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="8c0cc-107">为实现完整性，请确定打算公开到 COM 的程序集中的类型，尤其是当这些类型是公开到 .NET framework 中类型的子集时。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-107">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>  
  
     <span data-ttu-id="8c0cc-108">有关其他信息，请参阅[为互操作限定 .NET 类型](qualifying-net-types-for-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-108">For additional information, see [Qualifying .NET Types for Interoperation](qualifying-net-types-for-interoperation.md).</span></span>  
  
-   <span data-ttu-id="8c0cc-109">版本控制说明</span><span class="sxs-lookup"><span data-stu-id="8c0cc-109">Versioning instructions</span></span>  
  
     <span data-ttu-id="8c0cc-110">实现类接口（COM 互操作生成的接口）的托管类受版本控制限制。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-110">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>  
  
     <span data-ttu-id="8c0cc-111">有关如何使用类接口的指南，请参阅[类接口简介](com-callable-wrapper.md#introducing-the-class-interface)。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-111">For guidelines on using the class interface, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
-   <span data-ttu-id="8c0cc-112">部署说明</span><span class="sxs-lookup"><span data-stu-id="8c0cc-112">Deployment instructions</span></span>  
  
     <span data-ttu-id="8c0cc-113">发布者签名的具有强名称的程序集可安装到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-113">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="8c0cc-114">未签名程序集必须作为专用程序集安装在用户计算机上。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-114">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>  
  
     <span data-ttu-id="8c0cc-115">有关其他信息，请参阅[程序集安全注意事项](../app-domains/assembly-security-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-115">For additional information, see [Assembly Security Considerations](../app-domains/assembly-security-considerations.md).</span></span>  
  
-   <span data-ttu-id="8c0cc-116">类型库所含内容</span><span class="sxs-lookup"><span data-stu-id="8c0cc-116">Type library inclusion</span></span>  
  
     <span data-ttu-id="8c0cc-117">大多数类型在由 COM 应用程序使用时都需要类型库。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-117">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="8c0cc-118">可生成类型库或使 COM 开发人员执行此任务。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-118">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="8c0cc-119">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 为生成类型库提供以下选项：</span><span class="sxs-lookup"><span data-stu-id="8c0cc-119">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides the following options for generating a type library:</span></span>  
  
    -   [<span data-ttu-id="8c0cc-120">类型库导出程序</span><span class="sxs-lookup"><span data-stu-id="8c0cc-120">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)  
  
    -   [<span data-ttu-id="8c0cc-121">TypeLibConverter 类</span><span class="sxs-lookup"><span data-stu-id="8c0cc-121">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)  
  
    -   [<span data-ttu-id="8c0cc-122">程序集注册工具</span><span class="sxs-lookup"><span data-stu-id="8c0cc-122">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)  
  
    -   [<span data-ttu-id="8c0cc-123">.NET 服务安装工具</span><span class="sxs-lookup"><span data-stu-id="8c0cc-123">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)  
  
     <span data-ttu-id="8c0cc-124">无论选择的机制如何，生成的类型库中仅包含所提供程序集中定义的公共类型。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-124">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>  
  
     <span data-ttu-id="8c0cc-125">可将类型库打包为单独文件，或将其作为 Win32 资源文件嵌入基于 .NET 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-125">You can package a type library as a separate file or embed it as Win32 resource file within a .NET-based application.</span></span> <span data-ttu-id="8c0cc-126">Microsoft Visual Basic 6.0 自动执行此任务；但若 [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)]，必须手动嵌入类型库。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-126">Microsoft Visual Basic 6.0 performed this task for you automatically; however, when using [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)], you must embed your type library manually.</span></span> <span data-ttu-id="8c0cc-127">有关说明，请参阅[如何：将类型库作为 Win32 资源嵌入基于 .NET 的应用程序](https://msdn.microsoft.com/library/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-127">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](https://msdn.microsoft.com/library/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44(v=vs.100)).</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## <a name="type-library-exporter"></a><span data-ttu-id="8c0cc-128">类型库导出程序</span><span class="sxs-lookup"><span data-stu-id="8c0cc-128">Type Library Exporter</span></span>  
 <span data-ttu-id="8c0cc-129">[类型库导出程序 (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) 是命令行工具，可将程序集中包含的类和接口转换为 COM 类型库。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-129">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="8c0cc-130">一旦类的类型信息可用，COM 客户端就可创建 .NET 类的实例，并调用实例的方法，就像它是 COM 对象一样。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-130">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="8c0cc-131">Tlbexp.exe 一次转换整个程序集。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-131">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="8c0cc-132">不能使用 Tlbexp.exe 生成程序集中定义的类型子集的类型信息。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-132">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## <a name="typelibconverter-class"></a><span data-ttu-id="8c0cc-133">TypeLibConverter 类</span><span class="sxs-lookup"><span data-stu-id="8c0cc-133">TypeLibConverter Class</span></span>  
 <span data-ttu-id="8c0cc-134">位于 System.Runtime.Interop 命名空间中的 <xref:System.Runtime.InteropServices.TypeLibConverter> 类将程序集中包含的类和接口转换为 COM 类型库。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-134">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="8c0cc-135">此 API 生成与类型库导出程序相同的类型信息，如上节所述。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-135">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>  
  
 <span data-ttu-id="8c0cc-136">TypeLibConverter 类实现 <xref:System.Runtime.InteropServices.ITypeLibConverter>。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-136">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## <a name="assembly-registration-tool"></a><span data-ttu-id="8c0cc-137">程序集注册工具</span><span class="sxs-lookup"><span data-stu-id="8c0cc-137">Assembly Registration Tool</span></span>  
 <span data-ttu-id="8c0cc-138">[程序集注册工具 (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) 可在应用 /tlb: 选项时生成并注册类型库。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-138">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="8c0cc-139">COM 客户端要求在 Windows 注册表中安装类型库。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-139">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="8c0cc-140">如果不使用此选项，Regasm.exe 仅在程序集而非类型库中注册类型。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-140">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="8c0cc-141">在程序集中注册类型和注册类型库是不同的活动。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-141">Registering the types in an assembly and registering the type library are distinct activities.</span></span>  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## <a name="net-services-installation-tool"></a><span data-ttu-id="8c0cc-142">.NET 服务安装工具</span><span class="sxs-lookup"><span data-stu-id="8c0cc-142">.NET Services Installation Tool</span></span>  
 <span data-ttu-id="8c0cc-143">[.NET 服务安装工具 (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) 将托管类添加到 Windows 2000 组件服务，并在单个工具中组合多个任务。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-143">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="8c0cc-144">除加载和注册程序集外，Regsvcs.exe 还可将类型库生成、注册和安装到现有 COM+ 1.0 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c0cc-144">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0cc-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c0cc-145">See Also</span></span>  
 <xref:System.Runtime.InteropServices.TypeLibConverter>  
 <xref:System.Runtime.InteropServices.ITypeLibConverter>  
 [<span data-ttu-id="8c0cc-146">向 COM 公开 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="8c0cc-146">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="8c0cc-147">为互操作限定 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="8c0cc-147">Qualifying .NET Types for Interoperation</span></span>](qualifying-net-types-for-interoperation.md)  
 [<span data-ttu-id="8c0cc-148">类接口简介</span><span class="sxs-lookup"><span data-stu-id="8c0cc-148">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)  
 [<span data-ttu-id="8c0cc-149">程序集安全注意事项</span><span class="sxs-lookup"><span data-stu-id="8c0cc-149">Assembly Security Considerations</span></span>](../app-domains/assembly-security-considerations.md)  
 [<span data-ttu-id="8c0cc-150">Tlbexp.exe（类型库导出程序）</span><span class="sxs-lookup"><span data-stu-id="8c0cc-150">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)  
 [<span data-ttu-id="8c0cc-151">向 COM 注册程序集</span><span class="sxs-lookup"><span data-stu-id="8c0cc-151">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)  
 <span data-ttu-id="8c0cc-152">[如何：将类型库作为 Win32 资源嵌入应用程序](https://msdn.microsoft.com/library/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8c0cc-152">[How to: Embed Type Libraries as Win32 Resources in Applications](https://msdn.microsoft.com/library/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44(v=vs.100))</span></span>
