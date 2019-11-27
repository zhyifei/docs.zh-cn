---
title: IMetaDataAssemblyImport 接口
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436304"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="28bbd-102">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="28bbd-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="28bbd-103">提供访问和检查程序集清单内容的方法。</span><span class="sxs-lookup"><span data-stu-id="28bbd-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28bbd-104">方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-104">Methods</span></span>  
  
|<span data-ttu-id="28bbd-105">方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-105">Method</span></span>|<span data-ttu-id="28bbd-106">说明</span><span class="sxs-lookup"><span data-stu-id="28bbd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28bbd-107">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="28bbd-108">释放到指定枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="28bbd-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="28bbd-109">EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="28bbd-110">获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集所引用的程序集的 `mdAssemblyRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="28bbd-111">EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="28bbd-112">获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集引用的 COM 类型的 `mdExportedType` 标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="28bbd-113">EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="28bbd-114">获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集所引用的文件的 `mdFile` 标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="28bbd-115">EnumManifestResources 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="28bbd-116">获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集所引用资源的 `mdManifestResource` 标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="28bbd-117">FindAssembliesByName 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="28bbd-118">获取具有指定名称的程序集的 `mdAssemblyRef` 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="28bbd-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="28bbd-119">FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="28bbd-120">获取具有指定名称的 COM 类型的 `mdExportedType` 标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="28bbd-121">FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="28bbd-122">获取具有指定名称的资源的 `mdManifestResource` 标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="28bbd-123">GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="28bbd-124">获取当前元数据范围内的程序集的标记。</span><span class="sxs-lookup"><span data-stu-id="28bbd-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="28bbd-125">GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="28bbd-126">获取指定程序集的属性设置。</span><span class="sxs-lookup"><span data-stu-id="28bbd-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="28bbd-127">GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="28bbd-128">获取指定 `mdAssemblyRef` 标记的属性设置。</span><span class="sxs-lookup"><span data-stu-id="28bbd-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="28bbd-129">GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="28bbd-130">获取指定 COM 类型的属性设置。</span><span class="sxs-lookup"><span data-stu-id="28bbd-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="28bbd-131">GetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="28bbd-132">获取指定文件的属性设置。</span><span class="sxs-lookup"><span data-stu-id="28bbd-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="28bbd-133">GetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="28bbd-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="28bbd-134">获取指定的清单资源的属性设置。</span><span class="sxs-lookup"><span data-stu-id="28bbd-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28bbd-135">要求</span><span class="sxs-lookup"><span data-stu-id="28bbd-135">Requirements</span></span>  
 <span data-ttu-id="28bbd-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28bbd-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28bbd-137">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="28bbd-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28bbd-138">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="28bbd-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28bbd-139">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28bbd-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bbd-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28bbd-140">See also</span></span>

- [<span data-ttu-id="28bbd-141">元数据接口</span><span class="sxs-lookup"><span data-stu-id="28bbd-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="28bbd-142">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="28bbd-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
