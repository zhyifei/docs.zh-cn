---
title: "IALink 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IALink
helpviewer_keywords:
- IALink interface
ms.assetid: 50abd02d-6488-4815-999b-4fb89af4d568
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4c58c3aa5ca1ec2d8b3bc820b2b7a500604b4b7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ialink-interface"></a><span data-ttu-id="fe1a9-102">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="fe1a9-102">IALink Interface</span></span>
<span data-ttu-id="fe1a9-103">可帮助在构建.NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="fe1a9-103">Helps in constructing .NET Framework assemblies.</span></span> <span data-ttu-id="fe1a9-104">此外，该接口包含帮助为多模块程序集编写程序集清单、 签名程序集具有强名称，以及创建模块的方法。</span><span class="sxs-lookup"><span data-stu-id="fe1a9-104">Among other things, the interface contains methods that assist in writing assembly manifests for multi-module assemblies, signing assemblies with strong names, and creating netmodules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe1a9-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="fe1a9-105">In This Section</span></span>  
 [<span data-ttu-id="fe1a9-106">AddFile 方法 1</span><span class="sxs-lookup"><span data-stu-id="fe1a9-106">AddFile Method1</span></span>](../../../../docs/framework/unmanaged-api/alink/addfile-method.md)  
  
 [<span data-ttu-id="fe1a9-107">AddImport 方法 1</span><span class="sxs-lookup"><span data-stu-id="fe1a9-107">AddImport Method1</span></span>](../../../../docs/framework/unmanaged-api/alink/addimport-method.md)  
  
 [<span data-ttu-id="fe1a9-108">CloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-108">CloseAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/alink/closeassembly-method.md)  
  
 [<span data-ttu-id="fe1a9-109">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-109">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/alink/closeenum-method.md)  
  
 [<span data-ttu-id="fe1a9-110">EmbedResource 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-110">EmbedResource Method</span></span>](../../../../docs/framework/unmanaged-api/alink/embedresource-method.md)  
  
 [<span data-ttu-id="fe1a9-111">EmitAssemblyCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-111">EmitAssemblyCustomAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/alink/emitassemblycustomattribute-method.md)  
  
 [<span data-ttu-id="fe1a9-112">EmitManifest 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-112">EmitManifest Method</span></span>](../../../../docs/framework/unmanaged-api/alink/emitmanifest-method.md)  
  
 [<span data-ttu-id="fe1a9-113">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-113">EndMerge Method</span></span>](../../../../docs/framework/unmanaged-api/alink/endmerge-method.md)  
  
 [<span data-ttu-id="fe1a9-114">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-114">EnumCustomAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/alink/enumcustomattributes-method.md)  
  
 [<span data-ttu-id="fe1a9-115">EnumImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-115">EnumImportTypes Method</span></span>](../../../../docs/framework/unmanaged-api/alink/enumimporttypes-method.md)  
  
 [<span data-ttu-id="fe1a9-116">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-116">ExportNestedType Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exportnestedtype-method.md)  
  
 [<span data-ttu-id="fe1a9-117">ExportNestedTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-117">ExportNestedTypeForwarder Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exportnestedtypeforwarder-method.md)  
  
 [<span data-ttu-id="fe1a9-118">ExportType 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-118">ExportType Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)  
  
 [<span data-ttu-id="fe1a9-119">ExportTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-119">ExportTypeForwarder Method</span></span>](../../../../docs/framework/unmanaged-api/alink/exporttypeforwarder-method.md)  
  
 [<span data-ttu-id="fe1a9-120">FreeWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-120">FreeWin32ResBlob Method</span></span>](../../../../docs/framework/unmanaged-api/alink/freewin32resblob-method.md)  
  
 [<span data-ttu-id="fe1a9-121">GetAssemblyRefHash 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-121">GetAssemblyRefHash Method</span></span>](../../../../docs/framework/unmanaged-api/alink/getassemblyrefhash-method.md)  
  
 [<span data-ttu-id="fe1a9-122">GetResolutionScope 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-122">GetResolutionScope Method</span></span>](../../../../docs/framework/unmanaged-api/alink/getresolutionscope-method.md)  
  
 [<span data-ttu-id="fe1a9-123">GetScope 方法 1</span><span class="sxs-lookup"><span data-stu-id="fe1a9-123">GetScope Method1</span></span>](../../../../docs/framework/unmanaged-api/alink/getscope-method.md)  
  
 [<span data-ttu-id="fe1a9-124">GetWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-124">GetWin32ResBlob Method</span></span>](../../../../docs/framework/unmanaged-api/alink/getwin32resblob-method.md)  
  
 [<span data-ttu-id="fe1a9-125">ImportFile 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-125">ImportFile Method</span></span>](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)  
  
 [<span data-ttu-id="fe1a9-126">ImportFile2 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-126">ImportFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/alink/importfile2-method.md)  
  
 [<span data-ttu-id="fe1a9-127">ImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-127">ImportTypes Method</span></span>](../../../../docs/framework/unmanaged-api/alink/importtypes-method.md)  
  
 <span data-ttu-id="fe1a9-128">"Init 方法"</span><span class="sxs-lookup"><span data-stu-id="fe1a9-128">"Init Method"</span></span>  
  
 [<span data-ttu-id="fe1a9-129">LinkResource 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-129">LinkResource Method</span></span>](../../../../docs/framework/unmanaged-api/alink/linkresource-method.md)  
  
 [<span data-ttu-id="fe1a9-130">PreCloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-130">PreCloseAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/alink/precloseassembly-method.md)  
  
 [<span data-ttu-id="fe1a9-131">SetAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-131">SetAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/alink/setassemblyfile-method.md)  
  
 [<span data-ttu-id="fe1a9-132">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-132">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/alink/setassemblyprops-method.md)  
  
 [<span data-ttu-id="fe1a9-133">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="fe1a9-133">SetNonAssemblyFlags Method</span></span>](../../../../docs/framework/unmanaged-api/alink/setnonassemblyflags-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe1a9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe1a9-134">See Also</span></span>  
 [<span data-ttu-id="fe1a9-135">ALink API</span><span class="sxs-lookup"><span data-stu-id="fe1a9-135">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="fe1a9-136">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="fe1a9-136">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="fe1a9-137">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="fe1a9-137">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
