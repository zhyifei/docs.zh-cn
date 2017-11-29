---
title: "编译互操作项目"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc541911670c533caa97c645085ad09bde5eefdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="82c54-102">编译互操作项目</span><span class="sxs-lookup"><span data-stu-id="82c54-102">Compiling an Interop Project</span></span>
<span data-ttu-id="82c54-103">如果 COM 互操作项目引用一个或多个包含导入 COM 类型的程序集，则可以像其他任何托管项目一样进行编译。</span><span class="sxs-lookup"><span data-stu-id="82c54-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="82c54-104">可以在 Visual Studio 等开发环境中或使用命令行编译器时引用互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="82c54-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="82c54-105">无论哪种情况，若要正确编译，互操作程序集必须与其他项目文件位于同一个目录中。</span><span class="sxs-lookup"><span data-stu-id="82c54-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>  
  
 <span data-ttu-id="82c54-106">可以通过以下两种方式引用互操作程序集：</span><span class="sxs-lookup"><span data-stu-id="82c54-106">There are two ways to reference interop assemblies:</span></span>  
  
-   <span data-ttu-id="82c54-107">嵌入互操作类型：从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 和 [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] 开始，可以指示编译器将类型信息从互操作程序集嵌入到可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="82c54-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="82c54-108">这是推荐采用的方法。</span><span class="sxs-lookup"><span data-stu-id="82c54-108">This is the recommended technique.</span></span>  
  
-   <span data-ttu-id="82c54-109">部署互操作程序集：创建对互操作程序集的标准引用。</span><span class="sxs-lookup"><span data-stu-id="82c54-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="82c54-110">这种情况下，互操作程序集必须与应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="82c54-110">In this case, the interop assembly must be deployed with your application.</span></span>  
  
 <span data-ttu-id="82c54-111">这两种方法之间的差异在[在托管代码中使用 COM 类型 ](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)中有更详细的讨论。</span><span class="sxs-lookup"><span data-stu-id="82c54-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
 <span data-ttu-id="82c54-112">[演练：嵌入 Microsoft Office 程序集中的类型信息](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)和[演练：嵌入托管程序集中的类型 ](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)中演示了如何通过 Visual Studio 嵌入互操作类型。</span><span class="sxs-lookup"><span data-stu-id="82c54-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) and [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="82c54-113">若要使用命令行编译器引用互操作程序集，并将类型信息嵌入可执行文件中，请使用 [/link（C# 编译器选项）](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)或 [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) 编译器开关并指定互操作程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="82c54-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82c54-114">Visual C++ 应用程序无法嵌入类型信息，但它们可以与应用程序或加载项进行互操作。</span><span class="sxs-lookup"><span data-stu-id="82c54-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>  
  
 <span data-ttu-id="82c54-115">若要编译部署时包括主互操作程序集的应用程序，请使用“/reference”编译器开关并指定互操作程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="82c54-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c54-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82c54-116">See Also</span></span>  
 [<span data-ttu-id="82c54-117">向 .NET Framework 公开 COM 组件</span><span class="sxs-lookup"><span data-stu-id="82c54-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="82c54-118">语言独立性和与语言无关的组件</span><span class="sxs-lookup"><span data-stu-id="82c54-118">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="82c54-119">在托管代码中使用 COM 类型</span><span class="sxs-lookup"><span data-stu-id="82c54-119">Using COM Types in Managed Code</span></span>](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
 [<span data-ttu-id="82c54-120">演练：嵌入 Microsoft Office 程序集中的类型信息</span><span class="sxs-lookup"><span data-stu-id="82c54-120">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="82c54-121">演练：嵌入托管程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="82c54-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="82c54-122">将类型库作为程序集导入</span><span class="sxs-lookup"><span data-stu-id="82c54-122">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
