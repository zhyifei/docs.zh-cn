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
ms.openlocfilehash: 2a67f50fa1042e8d3957a9a0394507f260a328c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009010"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="3f7e4-102">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="3f7e4-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="3f7e4-103">提供访问和检查程序集清单内容的方法。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f7e4-104">方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-104">Methods</span></span>  
  
|<span data-ttu-id="3f7e4-105">方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-105">Method</span></span>|<span data-ttu-id="3f7e4-106">说明</span><span class="sxs-lookup"><span data-stu-id="3f7e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f7e4-107">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="3f7e4-108">释放到指定枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="3f7e4-109">EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="3f7e4-110">获取一个接口指针，该指针指向包含 `mdAssemblyRef` 当前元数据范围内的程序集所引用的程序集的标记。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="3f7e4-111">EnumExportedTypes 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="3f7e4-112">获取一个指向枚举数的接口指针，该枚举数包含 `mdExportedType` 当前元数据范围内的程序集引用的 COM 类型的标记。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="3f7e4-113">EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="3f7e4-114">获取一个接口指针，该指针指向一个枚举数，该枚举数包含 `mdFile` 当前元数据范围内的程序集所引用的文件的标记。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="3f7e4-115">EnumManifestResources 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="3f7e4-116">获取一个接口指针，该指针指向包含 `mdManifestResource` 当前元数据范围内的程序集所引用资源的标记的枚举数。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="3f7e4-117">FindAssembliesByName 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="3f7e4-118">获取 `mdAssemblyRef` 具有指定名称的程序集的标记数组。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="3f7e4-119">FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="3f7e4-120">获取 `mdExportedType` 具有指定名称的 COM 类型的标记。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="3f7e4-121">FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="3f7e4-122">获取 `mdManifestResource` 具有指定名称的资源的标记。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="3f7e4-123">GetAssemblyFromScope 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="3f7e4-124">获取当前元数据范围内的程序集的标记。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="3f7e4-125">GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="3f7e4-126">获取指定程序集的属性设置。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="3f7e4-127">GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="3f7e4-128">获取指定标记的属性设置 `mdAssemblyRef` 。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="3f7e4-129">GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="3f7e4-130">获取指定 COM 类型的属性设置。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="3f7e4-131">GetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="3f7e4-132">获取指定文件的属性设置。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="3f7e4-133">GetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="3f7e4-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="3f7e4-134">获取指定的清单资源的属性设置。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f7e4-135">要求</span><span class="sxs-lookup"><span data-stu-id="3f7e4-135">Requirements</span></span>  
 <span data-ttu-id="3f7e4-136">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f7e4-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f7e4-137">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="3f7e4-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f7e4-138">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3f7e4-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f7e4-139">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f7e4-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f7e4-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f7e4-140">See also</span></span>

- [<span data-ttu-id="3f7e4-141">元数据接口</span><span class="sxs-lookup"><span data-stu-id="3f7e4-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="3f7e4-142">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="3f7e4-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
