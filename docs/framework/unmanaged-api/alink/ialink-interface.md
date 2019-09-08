---
title: IALink 接口
ms.date: 03/30/2017
f1_keywords:
- IALink
helpviewer_keywords:
- IALink interface
ms.assetid: 50abd02d-6488-4815-999b-4fb89af4d568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7324ddb63f000f55a16c4963c808f658aa9098a7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787328"
---
# <a name="ialink-interface"></a><span data-ttu-id="a9010-102">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="a9010-102">IALink Interface</span></span>
<span data-ttu-id="a9010-103">有助于构造 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="a9010-103">Helps in constructing .NET Framework assemblies.</span></span> <span data-ttu-id="a9010-104">除此之外，接口还包含一些方法，这些方法可帮助编写多模块程序集的程序集清单、用强名称对程序集进行签名，并创建 netmodule。</span><span class="sxs-lookup"><span data-stu-id="a9010-104">Among other things, the interface contains methods that assist in writing assembly manifests for multi-module assemblies, signing assemblies with strong names, and creating netmodules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9010-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="a9010-105">In This Section</span></span>  
 [<span data-ttu-id="a9010-106">AddFile 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-106">AddFile Method</span></span>](addfile-method.md)  
  
 [<span data-ttu-id="a9010-107">AddImport 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-107">AddImport Method</span></span>](addimport-method.md)  
  
 [<span data-ttu-id="a9010-108">CloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-108">CloseAssembly Method</span></span>](closeassembly-method.md)  
  
 [<span data-ttu-id="a9010-109">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-109">CloseEnum Method</span></span>](closeenum-method.md)  
  
 [<span data-ttu-id="a9010-110">EmbedResource 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-110">EmbedResource Method</span></span>](embedresource-method.md)  
  
 [<span data-ttu-id="a9010-111">EmitAssemblyCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-111">EmitAssemblyCustomAttribute Method</span></span>](emitassemblycustomattribute-method.md)  
  
 [<span data-ttu-id="a9010-112">EmitManifest 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-112">EmitManifest Method</span></span>](emitmanifest-method.md)  
  
 [<span data-ttu-id="a9010-113">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-113">EndMerge Method</span></span>](endmerge-method.md)  
  
 [<span data-ttu-id="a9010-114">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-114">EnumCustomAttributes Method</span></span>](enumcustomattributes-method.md)  
  
 [<span data-ttu-id="a9010-115">EnumImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-115">EnumImportTypes Method</span></span>](enumimporttypes-method.md)  
  
 [<span data-ttu-id="a9010-116">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-116">ExportNestedType Method</span></span>](exportnestedtype-method.md)  
  
 [<span data-ttu-id="a9010-117">ExportNestedTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-117">ExportNestedTypeForwarder Method</span></span>](exportnestedtypeforwarder-method.md)  
  
 [<span data-ttu-id="a9010-118">ExportType 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-118">ExportType Method</span></span>](exporttype-method.md)  
  
 [<span data-ttu-id="a9010-119">ExportTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-119">ExportTypeForwarder Method</span></span>](exporttypeforwarder-method.md)  
  
 [<span data-ttu-id="a9010-120">FreeWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-120">FreeWin32ResBlob Method</span></span>](freewin32resblob-method.md)  
  
 [<span data-ttu-id="a9010-121">GetAssemblyRefHash 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-121">GetAssemblyRefHash Method</span></span>](getassemblyrefhash-method.md)  
  
 [<span data-ttu-id="a9010-122">GetResolutionScope 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-122">GetResolutionScope Method</span></span>](getresolutionscope-method.md)  
  
 [<span data-ttu-id="a9010-123">GetScope 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-123">GetScope Method</span></span>](getscope-method.md)  
  
 [<span data-ttu-id="a9010-124">GetWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-124">GetWin32ResBlob Method</span></span>](getwin32resblob-method.md)  
  
 [<span data-ttu-id="a9010-125">ImportFile 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-125">ImportFile Method</span></span>](importfile-method.md)  
  
 [<span data-ttu-id="a9010-126">ImportFile2 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-126">ImportFile2 Method</span></span>](importfile2-method.md)  
  
 [<span data-ttu-id="a9010-127">ImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-127">ImportTypes Method</span></span>](importtypes-method.md)  
  
 <span data-ttu-id="a9010-128">"Init 方法"</span><span class="sxs-lookup"><span data-stu-id="a9010-128">"Init Method"</span></span>  
  
 [<span data-ttu-id="a9010-129">LinkResource 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-129">LinkResource Method</span></span>](linkresource-method.md)  
  
 [<span data-ttu-id="a9010-130">PreCloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-130">PreCloseAssembly Method</span></span>](precloseassembly-method.md)  
  
 [<span data-ttu-id="a9010-131">SetAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-131">SetAssemblyFile Method</span></span>](setassemblyfile-method.md)  
  
 [<span data-ttu-id="a9010-132">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-132">SetAssemblyProps Method</span></span>](setassemblyprops-method.md)  
  
 [<span data-ttu-id="a9010-133">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="a9010-133">SetNonAssemblyFlags Method</span></span>](setnonassemblyflags-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9010-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9010-134">See also</span></span>

- [<span data-ttu-id="a9010-135">ALink API</span><span class="sxs-lookup"><span data-stu-id="a9010-135">ALink API</span></span>](index.md)
- [<span data-ttu-id="a9010-136">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="a9010-136">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a9010-137">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="a9010-137">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
