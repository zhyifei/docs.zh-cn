---
title: IMetaDataInfo::GetFileMapping 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84d53bd5bb9c0eca83b39fc9d1c83d93440e336b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645455"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="a7318-102">IMetaDataInfo::GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="a7318-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="a7318-103">获取内存区域的映射的文件和映射的类型。</span><span class="sxs-lookup"><span data-stu-id="a7318-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7318-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7318-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7318-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7318-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="a7318-106">[out]指向映射文件开头的指针。</span><span class="sxs-lookup"><span data-stu-id="a7318-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="a7318-107">[out]映射区域的大小。</span><span class="sxs-lookup"><span data-stu-id="a7318-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="a7318-108">如果`pdwMappingType`是`fmFlat`，这是文件的大小。</span><span class="sxs-lookup"><span data-stu-id="a7318-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="a7318-109">[out]一个[CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)值，该值指示映射的类型。</span><span class="sxs-lookup"><span data-stu-id="a7318-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="a7318-110">公共语言运行时 (CLR) 的当前实现总是返回`fmFlat`。</span><span class="sxs-lookup"><span data-stu-id="a7318-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="a7318-111">其他值保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="a7318-111">Other values are reserved for future use.</span></span> <span data-ttu-id="a7318-112">但是，你应当始终验证返回的值，因为其他值可能在将来版本中启用或服务版本。</span><span class="sxs-lookup"><span data-stu-id="a7318-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7318-113">返回值</span><span class="sxs-lookup"><span data-stu-id="a7318-113">Return Value</span></span>  
  
|<span data-ttu-id="a7318-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7318-114">HRESULT</span></span>|<span data-ttu-id="a7318-115">描述</span><span class="sxs-lookup"><span data-stu-id="a7318-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a7318-116">填充所有输出。</span><span class="sxs-lookup"><span data-stu-id="a7318-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="a7318-117">作为参数值传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="a7318-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="a7318-118">CLR 实现不能提供有关内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="a7318-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="a7318-119">这可能由于以下原因：</span><span class="sxs-lookup"><span data-stu-id="a7318-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="a7318-120">通过打开的元数据范围`ofWrite`或`ofCopyMemory`标志。</span><span class="sxs-lookup"><span data-stu-id="a7318-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="a7318-121">无需打开元数据范围`ofReadOnly`标志。</span><span class="sxs-lookup"><span data-stu-id="a7318-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="a7318-122">- [Imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法用来打开该文件的元数据部分。</span><span class="sxs-lookup"><span data-stu-id="a7318-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="a7318-123">-文件不是可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="a7318-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="a7318-124">**注意：** 这些条件依赖于 CLR 实现，并可能降低在将来版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="a7318-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7318-125">备注</span><span class="sxs-lookup"><span data-stu-id="a7318-125">Remarks</span></span>  
 <span data-ttu-id="a7318-126">内存的`ppvData`指向无效，将仅当基础元数据范围处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="a7318-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="a7318-127">为了使此方法时的调用的磁盘上文件的元数据映射到内存中工作[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，必须指定`ofReadOnly`标志，必须指定`ofWrite`或`ofCopyMemory`标志。</span><span class="sxs-lookup"><span data-stu-id="a7318-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="a7318-128">每个作用域的文件映射类型的选择是特定于给定的 clr 实现。</span><span class="sxs-lookup"><span data-stu-id="a7318-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="a7318-129">它不能由用户设置。</span><span class="sxs-lookup"><span data-stu-id="a7318-129">It cannot be set by the user.</span></span> <span data-ttu-id="a7318-130">CLR 的当前实现始终返回`fmFlat`在`pdwMappingType`，但这可能会更改在将来的 CLR 版本或将来的给定版本的 service release。</span><span class="sxs-lookup"><span data-stu-id="a7318-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="a7318-131">您应始终检查返回的值`pdwMappingType`，因为不同类型将具有不同的布局和偏移量。</span><span class="sxs-lookup"><span data-stu-id="a7318-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="a7318-132">不支持传递的任何三个参数为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a7318-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="a7318-133">该方法将返回`E_INVALIDARG`，并无输出来填充。</span><span class="sxs-lookup"><span data-stu-id="a7318-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="a7318-134">忽略映射类型或区域的大小可能会导致不正常程序终止。</span><span class="sxs-lookup"><span data-stu-id="a7318-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7318-135">要求</span><span class="sxs-lookup"><span data-stu-id="a7318-135">Requirements</span></span>  
 <span data-ttu-id="a7318-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7318-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7318-137">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7318-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7318-138">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a7318-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7318-139">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7318-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7318-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7318-140">See also</span></span>
- [<span data-ttu-id="a7318-141">IMetaDataInfo 接口</span><span class="sxs-lookup"><span data-stu-id="a7318-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="a7318-142">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="a7318-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
