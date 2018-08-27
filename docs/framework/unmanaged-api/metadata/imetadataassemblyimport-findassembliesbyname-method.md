---
title: IMetaDataAssemblyImport::FindAssembliesByName 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9babd5e50166be2c2d1b7bc32a5fc11d1ad8ba9
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930559"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="3cc38-102">IMetaDataAssemblyImport::FindAssembliesByName 方法</span><span class="sxs-lookup"><span data-stu-id="3cc38-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="3cc38-103">获取具有指定的程序集的数组`szAssemblyName`参数，并使用公共语言运行时 (CLR) 解析引用的标准规则。</span><span class="sxs-lookup"><span data-stu-id="3cc38-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc38-104">语法</span><span class="sxs-lookup"><span data-stu-id="3cc38-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3cc38-105">参数</span><span class="sxs-lookup"><span data-stu-id="3cc38-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="3cc38-106">[in]要在其中搜索给定的程序集的根目录。</span><span class="sxs-lookup"><span data-stu-id="3cc38-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="3cc38-107">如果此值设置为`null`，`FindAssembliesByName`将仅在全局程序集缓存中查找程序集。</span><span class="sxs-lookup"><span data-stu-id="3cc38-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="3cc38-108">[in]以分号分隔的子目录 （例如，"bin; bin2"），在其中搜索程序集的根目录下的列表。</span><span class="sxs-lookup"><span data-stu-id="3cc38-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="3cc38-109">除了默认探测规则中指定的探测这些目录。</span><span class="sxs-lookup"><span data-stu-id="3cc38-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="3cc38-110">[in]要查找的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3cc38-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="3cc38-111">此字符串的格式定义的类参考页中<xref:System.Reflection.AssemblyName>。</span><span class="sxs-lookup"><span data-stu-id="3cc38-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="3cc38-112">[in]类型的数组[IUnknown](/cpp/atl/iunknown)所要放入`IMetadataAssemblyImport`接口指针。</span><span class="sxs-lookup"><span data-stu-id="3cc38-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3cc38-113">[out]可将中的接口指针的最大数目`ppIUnk`。</span><span class="sxs-lookup"><span data-stu-id="3cc38-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="3cc38-114">[out]返回接口指针的数。</span><span class="sxs-lookup"><span data-stu-id="3cc38-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="3cc38-115">也就是说，数量的接口指针实际放置在`ppIUnk`。</span><span class="sxs-lookup"><span data-stu-id="3cc38-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cc38-116">返回值</span><span class="sxs-lookup"><span data-stu-id="3cc38-116">Return Value</span></span>  
  
|<span data-ttu-id="3cc38-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cc38-117">HRESULT</span></span>|<span data-ttu-id="3cc38-118">描述</span><span class="sxs-lookup"><span data-stu-id="3cc38-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3cc38-119">`FindAssembliesByName` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3cc38-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3cc38-120">没有程序集。</span><span class="sxs-lookup"><span data-stu-id="3cc38-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cc38-121">备注</span><span class="sxs-lookup"><span data-stu-id="3cc38-121">Remarks</span></span>  
 <span data-ttu-id="3cc38-122">指定程序集名称，`FindAssembliesByName`方法按照解析程序集引用的标准规则找到该程序集。</span><span class="sxs-lookup"><span data-stu-id="3cc38-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="3cc38-123">(有关详细信息，请参阅[运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。)`FindAssembliesByName`允许调用方配置的程序集冲突解决程序上下文，例如，应用程序基和专用搜索路径的各个方面。</span><span class="sxs-lookup"><span data-stu-id="3cc38-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="3cc38-124">`FindAssembliesByName`方法需要 CLR 初始化过程中，以便调用程序集的解析逻辑。</span><span class="sxs-lookup"><span data-stu-id="3cc38-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="3cc38-125">因此，您必须调用[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) （传递 COINITEE_DEFAULT） 之前，调用`FindAssembliesByName`，然后按照通过调用[CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc38-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="3cc38-126">`FindAssembliesByName` 返回[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)指针，指向包含程序集名称的程序集清单中传递的文件。</span><span class="sxs-lookup"><span data-stu-id="3cc38-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="3cc38-127">如果给定的程序集名称未完全指定 （例如，如果它不包含版本），可能返回多个程序集。</span><span class="sxs-lookup"><span data-stu-id="3cc38-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="3cc38-128">`FindAssembliesByName` 通常使用由编译器会尝试查找在编译时引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="3cc38-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc38-129">要求</span><span class="sxs-lookup"><span data-stu-id="3cc38-129">Requirements</span></span>  
 <span data-ttu-id="3cc38-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc38-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cc38-131">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3cc38-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3cc38-132">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3cc38-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3cc38-133">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cc38-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc38-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc38-134">See Also</span></span>  
 [<span data-ttu-id="3cc38-135">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="3cc38-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="3cc38-136">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="3cc38-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
