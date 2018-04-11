---
title: IMetaDataDispenser::OpenScopeOnMemory 方法
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d206863736387df04157ed752a6269b22a884b9
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="5bb75-102">IMetaDataDispenser::OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="5bb75-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="5bb75-103">将打开一个包含现有的元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="5bb75-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="5bb75-104">也就是说，此方法打开的现有数据视为元数据的内存的指定的区域。</span><span class="sxs-lookup"><span data-stu-id="5bb75-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb75-105">语法</span><span class="sxs-lookup"><span data-stu-id="5bb75-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bb75-106">参数</span><span class="sxs-lookup"><span data-stu-id="5bb75-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="5bb75-107">[in]指定的内存区域的开始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5bb75-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="5bb75-108">[in]内存区域，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="5bb75-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5bb75-109">[in]值为[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举，以打开指定的模式 （读取、 写入和等）。</span><span class="sxs-lookup"><span data-stu-id="5bb75-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="5bb75-110">[in]所需的元数据接口的 IID 要返回;调用方将使用该接口导入 （读取） 或发出 （写入） 元数据。</span><span class="sxs-lookup"><span data-stu-id="5bb75-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="5bb75-111">值`riid`必须指定"导入"发出"接口之一。</span><span class="sxs-lookup"><span data-stu-id="5bb75-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="5bb75-112">有效值为 IID_IMetaDataEmit、 IID_IMetaDataImport、 IID_IMetaDataAssemblyEmit、 IID_IMetaDataAssemblyImport、 IID_IMetaDataEmit2 或 IID_IMetaDataImport2。</span><span class="sxs-lookup"><span data-stu-id="5bb75-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="5bb75-113">[out]指向返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="5bb75-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bb75-114">备注</span><span class="sxs-lookup"><span data-stu-id="5bb75-114">Remarks</span></span>  
 <span data-ttu-id="5bb75-115">方法使用从一个"导入"接口，或添加到使用从"发出"界面中的一个方法，元数据的内存中副本可以进行查询。</span><span class="sxs-lookup"><span data-stu-id="5bb75-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="5bb75-116">`OpenScopeOnMemory`方法类似于是[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法，只不过感兴趣的元数据已存在在内存中，而不是磁盘上的文件中。</span><span class="sxs-lookup"><span data-stu-id="5bb75-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="5bb75-117">如果内存的目标区域不包含公共语言运行时 (CLR) 元数据，`OpenScopeOnMemory`方法将失败。</span><span class="sxs-lookup"><span data-stu-id="5bb75-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb75-118">要求</span><span class="sxs-lookup"><span data-stu-id="5bb75-118">Requirements</span></span>  
 <span data-ttu-id="5bb75-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bb75-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bb75-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5bb75-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bb75-121">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5bb75-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bb75-122">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bb75-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb75-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bb75-123">See Also</span></span>  
 [<span data-ttu-id="5bb75-124">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="5bb75-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="5bb75-125">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="5bb75-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="5bb75-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="5bb75-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="5bb75-127">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="5bb75-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="5bb75-128">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5bb75-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5bb75-129">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5bb75-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="5bb75-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="5bb75-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5bb75-131">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="5bb75-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
