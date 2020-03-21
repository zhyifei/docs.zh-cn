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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177805"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="ceaa1-102">IMetaDataAssemblyImport::FindAssembliesByName 方法</span><span class="sxs-lookup"><span data-stu-id="ceaa1-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="ceaa1-103">使用通用语言运行时 （CLR） 采用的标准规则解析引用，获取具有指定`szAssemblyName`参数的程序集数组。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceaa1-104">语法</span><span class="sxs-lookup"><span data-stu-id="ceaa1-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceaa1-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ceaa1-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="ceaa1-106">[在]要在其中搜索给定程序集的根目录。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="ceaa1-107">如果此值设置为`null`，`FindAssembliesByName`将仅在程序集的全局程序集缓存中查找。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="ceaa1-108">[在]在根目录下搜索程序集的分号分隔子目录（例如，"bin;bin2"）的列表。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="ceaa1-109">除了默认探测规则中指定的目录外，这些目录还被探测。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="ceaa1-110">[在]要查找的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="ceaa1-111">此字符串的格式在 的类引用页中<xref:System.Reflection.AssemblyName>定义。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="ceaa1-112">[在]放置`IMetadataAssemblyImport`接口指针的[I 未知](/cpp/atl/iunknown)类型的数组。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ceaa1-113">[出]可放置在 中的最大接口指针数`ppIUnk`。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="ceaa1-114">[出]返回的接口指针数。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="ceaa1-115">也就是说，实际上放置在 中的`ppIUnk`接口指针数。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ceaa1-116">返回值</span><span class="sxs-lookup"><span data-stu-id="ceaa1-116">Return Value</span></span>  
  
|<span data-ttu-id="ceaa1-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ceaa1-117">HRESULT</span></span>|<span data-ttu-id="ceaa1-118">说明</span><span class="sxs-lookup"><span data-stu-id="ceaa1-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ceaa1-119">`FindAssembliesByName`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ceaa1-120">没有程序集。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceaa1-121">备注</span><span class="sxs-lookup"><span data-stu-id="ceaa1-121">Remarks</span></span>  
 <span data-ttu-id="ceaa1-122">给定程序集名称，`FindAssembliesByName`该方法通过遵循解析程序集引用的标准规则来查找程序集。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="ceaa1-123">（有关详细信息，请参阅[运行时如何查找程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。`FindAssembliesByName`允许调用方配置程序集解析器上下文的各个方面，如应用程序库和专用搜索路径。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="ceaa1-124">该方法`FindAssembliesByName`要求在进程中初始化 CLR，以便调用程序集解析逻辑。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="ceaa1-125">因此，在调用`FindAssembliesByName`之前必须调用[Co初始化EEE（](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)传递COINITEE_DEFAULT），然后调用[CoUn初始化Cor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="ceaa1-126">`FindAssembliesByName`返回[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)指针，指向包含传入的程序集名称的程序集清单的文件。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="ceaa1-127">如果未完全指定给定程序集名称（例如，如果不包括版本），则可能会返回多个程序集。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="ceaa1-128">`FindAssembliesByName`尝试在编译时查找引用程序集的编译器通常使用。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceaa1-129">要求</span><span class="sxs-lookup"><span data-stu-id="ceaa1-129">Requirements</span></span>  
 <span data-ttu-id="ceaa1-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ceaa1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceaa1-131">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="ceaa1-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ceaa1-132">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ceaa1-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ceaa1-133">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceaa1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceaa1-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ceaa1-134">See also</span></span>

- [<span data-ttu-id="ceaa1-135">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="ceaa1-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="ceaa1-136">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="ceaa1-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
