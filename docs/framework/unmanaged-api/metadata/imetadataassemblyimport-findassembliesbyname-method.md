---
title: "IMetaDataAssemblyImport::FindAssembliesByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d6518fdcf1bef8eaea74818f69f46bb6df26e31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="f2c8b-102">IMetaDataAssemblyImport::FindAssembliesByName 方法</span><span class="sxs-lookup"><span data-stu-id="f2c8b-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="f2c8b-103">获取与指定的程序集的数组`szAssemblyName`参数，并使用由公共语言运行时 (CLR) 来解析引用的标准规则。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2c8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2c8b-104">Syntax</span></span>  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2c8b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2c8b-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="f2c8b-106">[in]要在其中搜索给定的程序集的根目录。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="f2c8b-107">如果此值设置为`null`，`FindAssembliesByName`将仅在全局程序集缓存中查找程序集。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="f2c8b-108">[in]以分号分隔 （例如，"bin; bin2"），目录下的子目录根，在其中搜索程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="f2c8b-109">除了默认探测规则中指定探测这些目录。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="f2c8b-110">[in]要查找的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="f2c8b-111">此字符串的格式定义中的类引用页<xref:System.Reflection.AssemblyName>。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f2c8b-112">[in]类型的数组 <<!--zzxref:IUnknown --> `IUnknown`> 在其中放入`IMetadataAssemblyImport`接口指针。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-112">[in] An array of type <<!--zzxref:IUnknown --> `IUnknown`> in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f2c8b-113">[out]最大数量的接口指针，可以放置在`ppIUnk`。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="f2c8b-114">[out]返回接口指针的数目。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="f2c8b-115">数量的接口指针，即实际放入`ppIUnk`。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2c8b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="f2c8b-116">Return Value</span></span>  
  
|<span data-ttu-id="f2c8b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2c8b-117">HRESULT</span></span>|<span data-ttu-id="f2c8b-118">描述</span><span class="sxs-lookup"><span data-stu-id="f2c8b-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f2c8b-119">`FindAssembliesByName`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f2c8b-120">没有程序集。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2c8b-121">备注</span><span class="sxs-lookup"><span data-stu-id="f2c8b-121">Remarks</span></span>  
 <span data-ttu-id="f2c8b-122">给定程序集名称，`FindAssembliesByName`方法找到按照标准规则以解析程序集引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="f2c8b-123">(有关详细信息，请参阅[运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。)`FindAssembliesByName`允许调用方的程序集冲突解决程序上下文中，如应用程序基和专用搜索路径的各个方面进行配置。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="f2c8b-124">`FindAssembliesByName`方法需要 CLR 初始化过程中，因此，为了调用程序集的解析逻辑。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="f2c8b-125">因此，必须调用[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) （在传递 COINITEE_DEFAULT） 之前调用`FindAssembliesByName`，然后通过调用按照[CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="f2c8b-126">`FindAssembliesByName`返回[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)指向包含程序集名称的程序集清单中传递的文件。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="f2c8b-127">如果给定的程序集名称未完全指定 （例如，如果它不包含版本），则可能会返回多个程序集。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="f2c8b-128">`FindAssembliesByName`通常由尝试查找在编译时引用的程序集的编译器使用。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2c8b-129">惠?</span><span class="sxs-lookup"><span data-stu-id="f2c8b-129">Requirements</span></span>  
 <span data-ttu-id="f2c8b-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2c8b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2c8b-131">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2c8b-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2c8b-132">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2c8b-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2c8b-133">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2c8b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c8b-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2c8b-134">See Also</span></span>  
 [<span data-ttu-id="f2c8b-135">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="f2c8b-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="f2c8b-136">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="f2c8b-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
