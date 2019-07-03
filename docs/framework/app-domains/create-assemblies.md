---
title: 创建程序集
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e544976b0b801b08af238b2aeb36b5611154379
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832904"
---
# <a name="creating-assemblies"></a><span data-ttu-id="77633-102">创建程序集</span><span class="sxs-lookup"><span data-stu-id="77633-102">Creating Assemblies</span></span>

<span data-ttu-id="77633-103">可以使用 Visual Studio 等 IDE 或 Windows 软件开发工具包 (SDK) 提供的编译器和工具来创建单文件或多文件程序集。</span><span class="sxs-lookup"><span data-stu-id="77633-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows Software Development Kit (SDK).</span></span> <span data-ttu-id="77633-104">最简单的程序集是具有简单名称并加载到单个应用程序域的单个文件。</span><span class="sxs-lookup"><span data-stu-id="77633-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="77633-105">此程序集不能被应用程序目录之外的其他程序集引用，并且不执行版本检查。</span><span class="sxs-lookup"><span data-stu-id="77633-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="77633-106">若要卸载该程序集组成的应用程序，只需删除它所在的目录即可。</span><span class="sxs-lookup"><span data-stu-id="77633-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="77633-107">对许多开发者来说，拥有这些功能的程序集能够满足他们部署应用程序的所有需要。</span><span class="sxs-lookup"><span data-stu-id="77633-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="77633-108">可以从多个代码模块和资源文件创建多文件程序集。</span><span class="sxs-lookup"><span data-stu-id="77633-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="77633-109">也可以创建可以由多个应用程序共享的程序集。</span><span class="sxs-lookup"><span data-stu-id="77633-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="77633-110">共享程序集必须具有强名称，并且可以部署在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="77633-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="77633-111">将代码模块和资源分组成程序集时有多个选项，具体取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="77633-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="77633-112">版本管理</span><span class="sxs-lookup"><span data-stu-id="77633-112">Versioning</span></span>

     <span data-ttu-id="77633-113">版本信息应相同的组模块。</span><span class="sxs-lookup"><span data-stu-id="77633-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="77633-114">部署</span><span class="sxs-lookup"><span data-stu-id="77633-114">Deployment</span></span>

     <span data-ttu-id="77633-115">支持你的部署模型的组代码模块和资源。</span><span class="sxs-lookup"><span data-stu-id="77633-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="77633-116">重用</span><span class="sxs-lookup"><span data-stu-id="77633-116">Reuse</span></span>

     <span data-ttu-id="77633-117">从逻辑上来说可以一起用于实现某个目的的组模块。</span><span class="sxs-lookup"><span data-stu-id="77633-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="77633-118">例如，不经常用于维护程序的类型和类构成的程序集可以放入同一程序集。</span><span class="sxs-lookup"><span data-stu-id="77633-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="77633-119">此外，要与多个应用程序共享的类型应归入一个程序集，并且此程序集必须使用强名称进行签名。</span><span class="sxs-lookup"><span data-stu-id="77633-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="77633-120">安全性</span><span class="sxs-lookup"><span data-stu-id="77633-120">Security</span></span>

     <span data-ttu-id="77633-121">包含需要相同安全权限的的类型的组模块。</span><span class="sxs-lookup"><span data-stu-id="77633-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="77633-122">范围</span><span class="sxs-lookup"><span data-stu-id="77633-122">Scoping</span></span>

     <span data-ttu-id="77633-123">所包含类型的可见性限为同一个程序集的组模块。</span><span class="sxs-lookup"><span data-stu-id="77633-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="77633-124">公共语言运行时程序集可用于非托管 COM 应用程序时，必须考虑特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="77633-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="77633-125">有关使用非托管代码的详细信息，请参阅[向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)。</span><span class="sxs-lookup"><span data-stu-id="77633-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="77633-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="77633-126">See also</span></span>

- [<span data-ttu-id="77633-127">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="77633-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="77633-128">程序集版本控制</span><span class="sxs-lookup"><span data-stu-id="77633-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)
- [<span data-ttu-id="77633-129">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="77633-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [<span data-ttu-id="77633-130">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="77633-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="77633-131">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="77633-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="77633-132">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="77633-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
