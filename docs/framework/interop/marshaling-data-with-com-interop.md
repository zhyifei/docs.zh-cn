---
title: "用 COM 互操作对数据进行封送处理"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 649936abfe149371445c77802bda2e72f558a41d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="b24a4-102">用 COM 互操作对数据进行封送处理</span><span class="sxs-lookup"><span data-stu-id="b24a4-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="b24a4-103">COM 互操作同时对在托管代码中使用 COM 对象和向 COM 公开托管对象提供支持。</span><span class="sxs-lookup"><span data-stu-id="b24a4-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="b24a4-104">对于将数据封送到 COM 和从 COM 中封送数据的支持是广泛的，并几乎总是提供正确的封送行为。</span><span class="sxs-lookup"><span data-stu-id="b24a4-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="b24a4-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 包括以下 COM 互操作工具：</span><span class="sxs-lookup"><span data-stu-id="b24a4-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
-   <span data-ttu-id="b24a4-106">[类型库导入程序 (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)，它将 COM 类型库转换为互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="b24a4-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="b24a4-107">从该程序集中，互操作封送处理服务生成包装器，该包装器在托管内存和非托管内存之间执行数据封送。</span><span class="sxs-lookup"><span data-stu-id="b24a4-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
-   <span data-ttu-id="b24a4-108">[类型库导出程序 (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)，它从程序集产生 COM 类型库，并生成在方法调用期间执行封送的包装器。</span><span class="sxs-lookup"><span data-stu-id="b24a4-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="b24a4-109">下列各节将介绍能够 （或必须） 为封送处理程序提供附加类型信息时自定义互操作包装器的进程的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="b24a4-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b24a4-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="b24a4-110">In This Section</span></span>  
<span data-ttu-id="b24a4-111">[如何： 手动创建包装器](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="b24a4-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="b24a4-112">描述如何在托管的源代码中手动创建 COM 包装器。</span><span class="sxs-lookup"><span data-stu-id="b24a4-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="b24a4-113">如何：将托管代码 DCOM 迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="b24a4-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="b24a4-114">描述如何将托管的 DCOM 代码迁移到 WCF，最安全的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b24a4-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b24a4-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="b24a4-115">Related Sections</span></span>  
 <span data-ttu-id="b24a4-116">[COM 数据类型](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-116">[COM Data Types](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-117">提供相应的托管和非托管数据类型。</span><span class="sxs-lookup"><span data-stu-id="b24a4-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="b24a4-118">[自定义 COM 可调用包装器](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-118">[Customizing COM Callable Wrappers](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-119">描述如何显式封送数据类型使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>在设计时属性。</span><span class="sxs-lookup"><span data-stu-id="b24a4-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="b24a4-120">[自定义运行时可调用包装器](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-120">[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-121">描述如何调整互操作程序集中类型的封送行为以及如何以手动方式定义 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="b24a4-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="b24a4-122">[高级 COM 互操作性](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-122">[Advanced COM Interoperability](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-123">提供一些链接，指向关于将 COM 组件并入 .NET Framework 应用程序中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b24a4-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="b24a4-124">[有关从程序集转换到类型库的摘要](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-124">[Assembly to Type Library Conversion Summary](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-125">描述从程序集到类型库的导出转换过程。</span><span class="sxs-lookup"><span data-stu-id="b24a4-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="b24a4-126">[有关从类型库转换到程序集的摘要](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-126">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-127">描述从类型库到程序集的导入转换过程。</span><span class="sxs-lookup"><span data-stu-id="b24a4-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="b24a4-128">[使用泛型类型进行交互操作](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="b24a4-128">[Interoperating Using Generic Types](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="b24a4-129">描述在使用用于 COM 互操作性的泛型类型时，哪些操作受支持。</span><span class="sxs-lookup"><span data-stu-id="b24a4-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
