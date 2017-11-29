---
title: "免注册 COM 互操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], interop
- COM interop, registration-free COM interop
- registration-free COM interop
- manifests [.NET Framework]
- registration-free activation
- object activation
- registration-free COM interop, about registration-free COM interop
ms.assetid: 90f308b9-82dc-414a-bce1-77e0155e56bd
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28ecb3419bddcc8e9a192b240a7bf90474314c1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="registration-free-com-interop"></a><span data-ttu-id="28519-102">免注册 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="28519-102">Registration-Free COM Interop</span></span>
<span data-ttu-id="28519-103">免注册 COM 互操作在不使用 Windows 注册表来存储程序集信息的情况下激活组件。</span><span class="sxs-lookup"><span data-stu-id="28519-103">Registration-free COM interop activates a component without using the Windows registry to store assembly information.</span></span> <span data-ttu-id="28519-104">不是在部署过程中在计算机上注册组件，而是在设计时创建包含有关绑定和激活信息的 Win32 样式清单文件。</span><span class="sxs-lookup"><span data-stu-id="28519-104">Instead of registering a component on a computer during deployment, you create Win32-style manifest files at design time that contain information about binding and activation.</span></span> <span data-ttu-id="28519-105">正是这些清单文件（而不是注册表项）指导对象的激活。</span><span class="sxs-lookup"><span data-stu-id="28519-105">These manifest files, rather than registry keys, direct the activation of an object.</span></span>  
  
 <span data-ttu-id="28519-106">不在部署期间注册程序集而使用免注册激活具有两大优势：</span><span class="sxs-lookup"><span data-stu-id="28519-106">Using registration-free activation for your assemblies instead of registering them during deployment offers two advantages:</span></span>  
  
-   <span data-ttu-id="28519-107">计算机上安装了多个 DLL 版本时，你可以控制要激活的版本。</span><span class="sxs-lookup"><span data-stu-id="28519-107">You can control which DLL version is activated when more than one version is installed on a computer.</span></span>  
  
-   <span data-ttu-id="28519-108">最终用户可以使用 XCOPY 或 FTP 将应用程序复制到计算机上适当的目录。</span><span class="sxs-lookup"><span data-stu-id="28519-108">End users can use XCOPY or FTP to copy your application to an appropriate directory on their computer.</span></span> <span data-ttu-id="28519-109">然后即可从该目录运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="28519-109">The application can then be run from that directory.</span></span>  
  
 <span data-ttu-id="28519-110">本节介绍免注册 COM 互操作所需的两种清单类型：应用程序清单和组件清单。</span><span class="sxs-lookup"><span data-stu-id="28519-110">This section describes the two types of manifests needed for registration-free COM interop: application and component manifests.</span></span> <span data-ttu-id="28519-111">这些清单是 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="28519-111">These manifests are XML files.</span></span> <span data-ttu-id="28519-112">应用程序清单由应用程序开发人员创建，包含描述程序集和程序集依赖项的元数据。</span><span class="sxs-lookup"><span data-stu-id="28519-112">An application manifest, which is created by an application developer, contains metadata that describes assemblies and assembly dependencies.</span></span> <span data-ttu-id="28519-113">组件清单由组件开发人员创建，包含 Windows 注册表中的其他信息。</span><span class="sxs-lookup"><span data-stu-id="28519-113">A component manifest, created by a component developer, contains information otherwise located in the Windows registry.</span></span>  
  
### <a name="requirements-for-registration-free-com-interop"></a><span data-ttu-id="28519-114">免注册 COM 互操作的要求</span><span class="sxs-lookup"><span data-stu-id="28519-114">Requirements for registration-free COM interop</span></span>  
  
1.  <span data-ttu-id="28519-115">对免注册 COM 互操作的支持根据库程序集的类型而略有差异；具体而言，因该程序集是非托管的（COM 并行）还是托管的（基于 NET）而异。</span><span class="sxs-lookup"><span data-stu-id="28519-115">Support for registration-free COM interop varies slightly depending on the type of library assembly; specifically, whether the assembly is unmanaged (COM side-by-side) or managed (.NET-based).</span></span> <span data-ttu-id="28519-116">下表显示每个程序集类型对操作系统和 .NET Framework 版本的要求。</span><span class="sxs-lookup"><span data-stu-id="28519-116">The following table shows the operating system and .NET Framework version requirements for each assembly type.</span></span>  
  
    |<span data-ttu-id="28519-117">程序集类型</span><span class="sxs-lookup"><span data-stu-id="28519-117">Assembly type</span></span>|<span data-ttu-id="28519-118">操作系统</span><span class="sxs-lookup"><span data-stu-id="28519-118">Operating system</span></span>|<span data-ttu-id="28519-119">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="28519-119">.NET Framework version</span></span>|  
    |-------------------|----------------------|----------------------------|  
    |<span data-ttu-id="28519-120">COM 并行</span><span class="sxs-lookup"><span data-stu-id="28519-120">COM side-by-side</span></span>|<span data-ttu-id="28519-121">Microsoft Windows XP</span><span class="sxs-lookup"><span data-stu-id="28519-121">Microsoft Windows XP</span></span>|<span data-ttu-id="28519-122">不要求。</span><span class="sxs-lookup"><span data-stu-id="28519-122">Not required.</span></span>|  
    |<span data-ttu-id="28519-123">基于 .NET</span><span class="sxs-lookup"><span data-stu-id="28519-123">.NET-based</span></span>|<span data-ttu-id="28519-124">带有 SP2 的 Windows XP</span><span class="sxs-lookup"><span data-stu-id="28519-124">Windows XP with SP2</span></span>|<span data-ttu-id="28519-125">NET Framework 1.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="28519-125">NET Framework version 1.1 or later.</span></span>|  
  
     <span data-ttu-id="28519-126">Windows Server 2003 系列还支持基于 .NET 的程序集采用免注册 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="28519-126">The Windows Server 2003 family also supports registration-free COM interop for .NET-based assemblies.</span></span>  
  
     <span data-ttu-id="28519-127">要使基于 .NET 的类与 COM 的免注册激活兼容，类必须具有默认的构造函数，并且必须是公共类。</span><span class="sxs-lookup"><span data-stu-id="28519-127">For a .NET-based class to be compatible with registry-free activation from COM, the class must have a default constructor and must be public.</span></span>  
  
### <a name="configuring-com-components-for-registration-free-activation"></a><span data-ttu-id="28519-128">将 COM 组件配置为免注册激活</span><span class="sxs-lookup"><span data-stu-id="28519-128">Configuring COM components for registration-free activation</span></span>  
  
1.  <span data-ttu-id="28519-129">要使 COM 组件参与免注册激活，必需将其作为并行程序集进行部署。</span><span class="sxs-lookup"><span data-stu-id="28519-129">For a COM component to participate in registration-free activation, it must be deployed as a side-by-side assembly.</span></span> <span data-ttu-id="28519-130">并行程序集是非托管程序集。</span><span class="sxs-lookup"><span data-stu-id="28519-130">Side-by-side assemblies are unmanaged assemblies.</span></span>  <span data-ttu-id="28519-131">有关详细信息，请参阅[使用通过并行集](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28519-131">For more information, see [Using Side-by-side Assemblies](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx).</span></span>  
  
     <span data-ttu-id="28519-132">要使用 COM 并行程序集，基于 .NET 的应用程序的开发人员必须提供一个包含绑定和激活信息的应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="28519-132">To use COM side-by-side assemblies, a .NET-based application developer must provide an application manifest, which contains the binding and activation information.</span></span> <span data-ttu-id="28519-133">Windows XP 操作系统内置对非托管并行程序集的支持。</span><span class="sxs-lookup"><span data-stu-id="28519-133">Support for unmanaged side-by-side assemblies is built into the Windows XP operating system.</span></span> <span data-ttu-id="28519-134">当要激活的组件不在注册表中时，操作系统支持的 COM 运行时将扫描应用程序清单以查找激活信息。</span><span class="sxs-lookup"><span data-stu-id="28519-134">The COM runtime, supported by the operating system, scans an application manifest for activation information when the component being activated is not in the registry.</span></span>  
  
     <span data-ttu-id="28519-135">Windows XP 上安装的 COM 组件可以选择进行免注册激活。</span><span class="sxs-lookup"><span data-stu-id="28519-135">Registration-free activation is optional for COM components installed on Windows XP.</span></span> <span data-ttu-id="28519-136">将通过并行程序集添加到应用程序的详细说明，请参阅[使用通过并行集](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28519-136">For detailed instructions on adding a side-by-side assembly to an application, see [Using Side-by-side Assemblies](https://msdn.microsoft.com/library/windows/desktop/aa376618.aspx).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28519-137">并行执行是一项 .NET Framework 功能，它使得多个版本的运行时，以及使用同一个运行时版本的多个版本的应用程序和组件，能够在同一台计算机上同时运行。</span><span class="sxs-lookup"><span data-stu-id="28519-137">Side-by-side execution is a .NET Framework feature that enables multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, to run on the same computer at the same time.</span></span> <span data-ttu-id="28519-138">并行执行和并行程序集是提供并行功能的两种不同机制。</span><span class="sxs-lookup"><span data-stu-id="28519-138">Side-by-side execution and side-by-side assemblies are different mechanisms for providing side-by-side functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28519-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28519-139">See Also</span></span>  
 [<span data-ttu-id="28519-140">如何：配置基于 .NET Framework 的 COM 组件以进行免注册激活</span><span class="sxs-lookup"><span data-stu-id="28519-140">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](../../../docs/framework/interop/configure-net-framework-based-com-components-for-reg.md)
