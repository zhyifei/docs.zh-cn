---
title: "IMetaDataAssemblyImport 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 992b588d16bc221f6b72044da40d09fbb6894511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="eeb3b-102">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="eeb3b-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="eeb3b-103">提供访问和检查程序集清单内容的方法。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eeb3b-104">方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-104">Methods</span></span>  
  
|<span data-ttu-id="eeb3b-105">方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-105">Method</span></span>|<span data-ttu-id="eeb3b-106">描述</span><span class="sxs-lookup"><span data-stu-id="eeb3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eeb3b-107">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="eeb3b-108">释放指定的枚举的句柄。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="eeb3b-109">EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="eeb3b-110">获取枚举数，其中包含的接口指针`mdAssemblyRef`由当前的元数据范围内的程序集引用的程序集的令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="eeb3b-111">EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="eeb3b-112">获取枚举数，其中包含的接口指针`mdExportedType`由当前的元数据范围内的程序集引用的 COM 类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="eeb3b-113">EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="eeb3b-114">获取枚举数，其中包含的接口指针`mdFile`由当前的元数据范围内的程序集所引用的文件的令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="eeb3b-115">EnumManifestResources 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="eeb3b-116">获取枚举数，其中包含的接口指针`mdManifestResource`由当前的元数据范围内的程序集引用的资源的令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="eeb3b-117">FindAssembliesByName 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="eeb3b-118">获取一个数组`mdAssemblyRef`具有指定名称的程序集的令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="eeb3b-119">FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="eeb3b-120">获取`mdExportedType`标记，表示具有指定名称的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="eeb3b-121">FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="eeb3b-122">获取`mdManifestResource`标记，表示具有指定名称的资源。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="eeb3b-123">GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="eeb3b-124">当前的元数据范围内获取程序集的令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="eeb3b-125">GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="eeb3b-126">获取指定的程序集的属性设置。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="eeb3b-127">GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="eeb3b-128">获取指定的属性设置`mdAssemblyRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="eeb3b-129">GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="eeb3b-130">获取指定的 COM 类型的属性设置。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="eeb3b-131">GetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="eeb3b-132">获取指定的文件的属性设置。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="eeb3b-133">GetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="eeb3b-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="eeb3b-134">获取指定的清单资源的属性设置。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eeb3b-135">惠?</span><span class="sxs-lookup"><span data-stu-id="eeb3b-135">Requirements</span></span>  
 <span data-ttu-id="eeb3b-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eeb3b-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb3b-137">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eeb3b-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eeb3b-138">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eeb3b-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eeb3b-139">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb3b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb3b-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb3b-140">See Also</span></span>  
 [<span data-ttu-id="eeb3b-141">元数据接口</span><span class="sxs-lookup"><span data-stu-id="eeb3b-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="eeb3b-142">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="eeb3b-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
