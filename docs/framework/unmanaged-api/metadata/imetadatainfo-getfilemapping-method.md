---
title: "IMetaDataInfo::GetFileMapping 方法"
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
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f974230dc5ddf2a663f05fc06850f49f1de6e773
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="4acbb-102">IMetaDataInfo::GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="4acbb-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="4acbb-103">获取映射的文件和的映射的类型的内存区域。</span><span class="sxs-lookup"><span data-stu-id="4acbb-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4acbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="4acbb-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4acbb-105">参数</span><span class="sxs-lookup"><span data-stu-id="4acbb-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="4acbb-106">[out]指向映射文件的开头的指针。</span><span class="sxs-lookup"><span data-stu-id="4acbb-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="4acbb-107">[out]映射区域的大小。</span><span class="sxs-lookup"><span data-stu-id="4acbb-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="4acbb-108">如果`pdwMappingType`是`fmFlat`，这是文件的大小。</span><span class="sxs-lookup"><span data-stu-id="4acbb-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="4acbb-109">[out]A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)值，该值指示的映射的类型。</span><span class="sxs-lookup"><span data-stu-id="4acbb-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="4acbb-110">公共语言运行时 (CLR) 的当前实现始终返回`fmFlat`。</span><span class="sxs-lookup"><span data-stu-id="4acbb-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="4acbb-111">其他值进行保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="4acbb-111">Other values are reserved for future use.</span></span> <span data-ttu-id="4acbb-112">但是，您应始终验证返回的值，因为其他值可能在将来版本中启用或服务版本。</span><span class="sxs-lookup"><span data-stu-id="4acbb-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4acbb-113">返回值</span><span class="sxs-lookup"><span data-stu-id="4acbb-113">Return Value</span></span>  
  
|<span data-ttu-id="4acbb-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4acbb-114">HRESULT</span></span>|<span data-ttu-id="4acbb-115">描述</span><span class="sxs-lookup"><span data-stu-id="4acbb-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4acbb-116">填充所有输出。</span><span class="sxs-lookup"><span data-stu-id="4acbb-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="4acbb-117">作为自变量值传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="4acbb-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="4acbb-118">CLR 实现无法提供有关内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="4acbb-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="4acbb-119">这可能是由于以下原因：</span><span class="sxs-lookup"><span data-stu-id="4acbb-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="4acbb-120">元数据范围通过打开`ofWrite`或`ofCopyMemory`标志。</span><span class="sxs-lookup"><span data-stu-id="4acbb-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="4acbb-121">元数据范围已打开情况下会`ofReadOnly`标志。</span><span class="sxs-lookup"><span data-stu-id="4acbb-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="4acbb-122">- [Imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法用于打开该文件的元数据部分。</span><span class="sxs-lookup"><span data-stu-id="4acbb-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="4acbb-123">-该文件不是可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="4acbb-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="4acbb-124">**注意：**这些条件依赖于 CLR 实现中，和可能削弱在将来 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="4acbb-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4acbb-125">备注</span><span class="sxs-lookup"><span data-stu-id="4acbb-125">Remarks</span></span>  
 <span data-ttu-id="4acbb-126">内存的`ppvData`指向是有效的只要基础元数据范围内处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="4acbb-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="4acbb-127">按顺序才能起作用，当你将磁盘上文件的元数据映射到内存中通过调用此方法[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，你必须指定`ofReadOnly`标志，你必须指定`ofWrite`或`ofCopyMemory`标志。</span><span class="sxs-lookup"><span data-stu-id="4acbb-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="4acbb-128">特定于给定的 CLR 实现的每个作用域的文件映射类型选择。</span><span class="sxs-lookup"><span data-stu-id="4acbb-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="4acbb-129">它不能通过用户设置。</span><span class="sxs-lookup"><span data-stu-id="4acbb-129">It cannot be set by the user.</span></span> <span data-ttu-id="4acbb-130">CLR 的当前实现始终返回`fmFlat`中`pdwMappingType`，但这可能会更改在将来版本的 CLR，或在将来的给定版本的服务版本。</span><span class="sxs-lookup"><span data-stu-id="4acbb-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="4acbb-131">你应始终检查返回的值， `pdwMappingType`，因为不同的类型将具有不同的布局和偏移量。</span><span class="sxs-lookup"><span data-stu-id="4acbb-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="4acbb-132">不支持传递对于所有三个参数为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4acbb-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="4acbb-133">该方法返回`E_INVALIDARG`，并无输出来填充。</span><span class="sxs-lookup"><span data-stu-id="4acbb-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="4acbb-134">忽略映射类型或区域的大小可能会导致程序的异常终止。</span><span class="sxs-lookup"><span data-stu-id="4acbb-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4acbb-135">惠?</span><span class="sxs-lookup"><span data-stu-id="4acbb-135">Requirements</span></span>  
 <span data-ttu-id="4acbb-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4acbb-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4acbb-137">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4acbb-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4acbb-138">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4acbb-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4acbb-139">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4acbb-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4acbb-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="4acbb-140">See Also</span></span>  
 [<span data-ttu-id="4acbb-141">IMetaDataInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4acbb-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="4acbb-142">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="4acbb-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
