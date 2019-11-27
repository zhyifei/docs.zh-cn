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
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436173"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="e77e3-102">IMetaDataInfo::GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="e77e3-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="e77e3-103">获取映射文件的内存区域和映射类型。</span><span class="sxs-lookup"><span data-stu-id="e77e3-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="e77e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e77e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="e77e3-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="e77e3-106">弄指向映射文件的开头的指针。</span><span class="sxs-lookup"><span data-stu-id="e77e3-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="e77e3-107">弄映射区域的大小。</span><span class="sxs-lookup"><span data-stu-id="e77e3-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="e77e3-108">如果 `fmFlat``pdwMappingType`，则这是文件的大小。</span><span class="sxs-lookup"><span data-stu-id="e77e3-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="e77e3-109">弄指示映射类型的[CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="e77e3-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="e77e3-110">公共语言运行时（CLR）的当前实现始终返回 `fmFlat`。</span><span class="sxs-lookup"><span data-stu-id="e77e3-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="e77e3-111">保留其他值以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="e77e3-111">Other values are reserved for future use.</span></span> <span data-ttu-id="e77e3-112">但是，应始终验证返回的值，因为在将来的版本或服务版本中可能会启用其他值。</span><span class="sxs-lookup"><span data-stu-id="e77e3-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e77e3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e77e3-113">Return Value</span></span>  
  
|<span data-ttu-id="e77e3-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e77e3-114">HRESULT</span></span>|<span data-ttu-id="e77e3-115">说明</span><span class="sxs-lookup"><span data-stu-id="e77e3-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e77e3-116">所有输出都已填充。</span><span class="sxs-lookup"><span data-stu-id="e77e3-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="e77e3-117">将 NULL 作为参数值传递。</span><span class="sxs-lookup"><span data-stu-id="e77e3-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="e77e3-118">CLR 实现无法提供有关内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="e77e3-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="e77e3-119">这可能是由以下原因引起的：</span><span class="sxs-lookup"><span data-stu-id="e77e3-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="e77e3-120">-元数据范围是用 `ofWrite` 或 `ofCopyMemory` 标志打开的。</span><span class="sxs-lookup"><span data-stu-id="e77e3-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="e77e3-121">-元数据范围在未 `ofReadOnly` 标志的情况下打开。</span><span class="sxs-lookup"><span data-stu-id="e77e3-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="e77e3-122">- [IMetaDataDispenser：： OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法仅用于打开文件的元数据部分。</span><span class="sxs-lookup"><span data-stu-id="e77e3-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="e77e3-123">-此文件不是可移植的可执行（PE）文件。</span><span class="sxs-lookup"><span data-stu-id="e77e3-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="e77e3-124">**注意：** 这些条件依赖于 CLR 实现，并且可能会在 CLR 的未来版本中减弱。</span><span class="sxs-lookup"><span data-stu-id="e77e3-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e77e3-125">备注</span><span class="sxs-lookup"><span data-stu-id="e77e3-125">Remarks</span></span>  
 <span data-ttu-id="e77e3-126">`ppvData` 指向的内存仅在基础元数据范围打开时有效。</span><span class="sxs-lookup"><span data-stu-id="e77e3-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="e77e3-127">为了使此方法正常工作，当你通过调用[IMetaDataDispenser：： OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法将磁盘上的文件的元数据映射到内存中时，必须指定 `ofReadOnly` 标志，并且不得指定 `ofWrite` 或 `ofCopyMemory` 标志。</span><span class="sxs-lookup"><span data-stu-id="e77e3-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="e77e3-128">每个作用域的文件映射类型选择特定于 CLR 的给定实现。</span><span class="sxs-lookup"><span data-stu-id="e77e3-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="e77e3-129">它不能由用户设置。</span><span class="sxs-lookup"><span data-stu-id="e77e3-129">It cannot be set by the user.</span></span> <span data-ttu-id="e77e3-130">CLR 的当前实现始终在 `pdwMappingType`中返回 `fmFlat`，但这可能会在将来版本的 CLR 或未来版本的服务版本中发生更改。</span><span class="sxs-lookup"><span data-stu-id="e77e3-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="e77e3-131">应始终在 `pdwMappingType`中检查返回的值，因为不同的类型将具有不同的布局和偏移量。</span><span class="sxs-lookup"><span data-stu-id="e77e3-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="e77e3-132">不支持为这三个参数中的任何一个传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="e77e3-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="e77e3-133">方法返回 `E_INVALIDARG`，而不填充任何输出。</span><span class="sxs-lookup"><span data-stu-id="e77e3-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="e77e3-134">忽略映射类型或区域大小可能会导致程序终止异常。</span><span class="sxs-lookup"><span data-stu-id="e77e3-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e77e3-135">要求</span><span class="sxs-lookup"><span data-stu-id="e77e3-135">Requirements</span></span>  
 <span data-ttu-id="e77e3-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e77e3-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e77e3-137">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="e77e3-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e77e3-138">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e77e3-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e77e3-139">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e77e3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77e3-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e77e3-140">See also</span></span>

- [<span data-ttu-id="e77e3-141">IMetaDataInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e77e3-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="e77e3-142">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="e77e3-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
