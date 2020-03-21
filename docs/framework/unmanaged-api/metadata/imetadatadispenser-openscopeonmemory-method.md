---
title: IMetaDataDispenser::OpenScopeOnMemory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175923"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="d3958-102">IMetaDataDispenser::OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="d3958-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="d3958-103">打开包含现有元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="d3958-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="d3958-104">也就是说，此方法将打开指定内存区域，其中现有数据被视为元数据。</span><span class="sxs-lookup"><span data-stu-id="d3958-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3958-105">语法</span><span class="sxs-lookup"><span data-stu-id="d3958-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3958-106">parameters</span><span class="sxs-lookup"><span data-stu-id="d3958-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="d3958-107">[在]指定内存区域的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d3958-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="d3958-108">[在]内存区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d3958-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d3958-109">[在][CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举的值，用于指定打开的模式（读取、写入等）。</span><span class="sxs-lookup"><span data-stu-id="d3958-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="d3958-110">[在]要返回的所需元数据接口的 IID;调用方将使用接口导入（读取）或发出（写入）元数据。</span><span class="sxs-lookup"><span data-stu-id="d3958-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="d3958-111">的值`riid`必须指定其中一个"导入"或"发射"接口。</span><span class="sxs-lookup"><span data-stu-id="d3958-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="d3958-112">有效值IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2或IID_IMetaDataImport2。</span><span class="sxs-lookup"><span data-stu-id="d3958-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="d3958-113">[出]指向返回接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d3958-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3958-114">备注</span><span class="sxs-lookup"><span data-stu-id="d3958-114">Remarks</span></span>  
 <span data-ttu-id="d3958-115">可以使用"导入"接口之一的方法查询元数据的内存副本，也可以添加到使用"emit"接口之一的方法。</span><span class="sxs-lookup"><span data-stu-id="d3958-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="d3958-116">该方法`OpenScopeOnMemory`类似于[IMetaDataDispenser：：openScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，只不过感兴趣的元数据已存在于内存中，而不是磁盘上的文件中。</span><span class="sxs-lookup"><span data-stu-id="d3958-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="d3958-117">如果内存的目标区域不包含通用语言运行时 （CLR） 元数据，则`OpenScopeOnMemory`该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="d3958-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3958-118">要求</span><span class="sxs-lookup"><span data-stu-id="d3958-118">Requirements</span></span>  
 <span data-ttu-id="d3958-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3958-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3958-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="d3958-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3958-121">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d3958-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3958-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3958-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3958-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3958-123">See also</span></span>

- [<span data-ttu-id="d3958-124">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="d3958-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="d3958-125">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="d3958-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="d3958-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d3958-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="d3958-127">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="d3958-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="d3958-128">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d3958-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d3958-129">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d3958-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d3958-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d3958-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d3958-131">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d3958-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
