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
ms.openlocfilehash: 04e0fabfc0d70c9d922e0715f32bd07237ce8741
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442311"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="32d5f-102">IMetaDataDispenser::OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="32d5f-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="32d5f-103">打开包含现有元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="32d5f-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="32d5f-104">也就是说，此方法将打开一个指定的内存区域，其中的现有数据将被视为元数据。</span><span class="sxs-lookup"><span data-stu-id="32d5f-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d5f-105">语法</span><span class="sxs-lookup"><span data-stu-id="32d5f-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32d5f-106">参数</span><span class="sxs-lookup"><span data-stu-id="32d5f-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="32d5f-107">中指定内存区域起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="32d5f-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="32d5f-108">中内存区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="32d5f-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="32d5f-109">中[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举的值，该值指定用于打开的模式（读取、写入等）。</span><span class="sxs-lookup"><span data-stu-id="32d5f-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="32d5f-110">中要返回的所需元数据接口的 IID;调用方将使用接口导入（读取）或发出（写入）元数据。</span><span class="sxs-lookup"><span data-stu-id="32d5f-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="32d5f-111">`riid` 的值必须指定一个 "导入" 或 "发出" 接口。</span><span class="sxs-lookup"><span data-stu-id="32d5f-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="32d5f-112">有效值为 IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2 或 IID_IMetaDataImport2。</span><span class="sxs-lookup"><span data-stu-id="32d5f-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="32d5f-113">弄指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="32d5f-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32d5f-114">备注</span><span class="sxs-lookup"><span data-stu-id="32d5f-114">Remarks</span></span>  
 <span data-ttu-id="32d5f-115">可以使用 "导入" 接口中的方法查询元数据的内存中副本，或使用 "发出" 接口之一中的方法将其添加到中。</span><span class="sxs-lookup"><span data-stu-id="32d5f-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="32d5f-116">`OpenScopeOnMemory` 方法类似于[IMetaDataDispenser：： OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，不同之处在于相关元数据已存在于内存中，而不是磁盘上的文件中。</span><span class="sxs-lookup"><span data-stu-id="32d5f-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="32d5f-117">如果内存的目标区域不包含公共语言运行时（CLR）元数据，则 `OpenScopeOnMemory` 方法将失败。</span><span class="sxs-lookup"><span data-stu-id="32d5f-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d5f-118">要求</span><span class="sxs-lookup"><span data-stu-id="32d5f-118">Requirements</span></span>  
 <span data-ttu-id="32d5f-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32d5f-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d5f-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="32d5f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32d5f-121">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="32d5f-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32d5f-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d5f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d5f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32d5f-123">See also</span></span>

- [<span data-ttu-id="32d5f-124">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="32d5f-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="32d5f-125">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="32d5f-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="32d5f-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="32d5f-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="32d5f-127">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="32d5f-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="32d5f-128">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="32d5f-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="32d5f-129">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="32d5f-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="32d5f-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="32d5f-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="32d5f-131">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="32d5f-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
