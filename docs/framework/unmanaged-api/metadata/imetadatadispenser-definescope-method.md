---
title: "IMetaDataDispenser::DefineScope 方法"
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
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: df7a700a5747f88f14cbfa4d10f1f4d0c2a14ab7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="47427-102">IMetaDataDispenser::DefineScope 方法</span><span class="sxs-lookup"><span data-stu-id="47427-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="47427-103">可以在其中创建新的元数据的内存中创建一个新的区域。</span><span class="sxs-lookup"><span data-stu-id="47427-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47427-104">语法</span><span class="sxs-lookup"><span data-stu-id="47427-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47427-105">参数</span><span class="sxs-lookup"><span data-stu-id="47427-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="47427-106">[in]要创建版本的元数据结构的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="47427-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="47427-107">此值必须是.NET Framework 2.0 版的 CLSID_CorMetaDataRuntime。</span><span class="sxs-lookup"><span data-stu-id="47427-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="47427-108">[in]指定选项的标志。</span><span class="sxs-lookup"><span data-stu-id="47427-108">[in] Flags that specify options.</span></span> <span data-ttu-id="47427-109">此值必须为零的.NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="47427-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="47427-110">[in]所需的元数据接口的 IID 要返回;调用方将使用接口创建新的元数据。</span><span class="sxs-lookup"><span data-stu-id="47427-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="47427-111">值`riid`必须指定"发出"接口之一。</span><span class="sxs-lookup"><span data-stu-id="47427-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="47427-112">有效值为 IID_IMetaDataEmit、 IID_IMetaDataAssemblyEmit 或 IID_IMetaDataEmit2。</span><span class="sxs-lookup"><span data-stu-id="47427-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="47427-113">[out]指向返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="47427-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47427-114">备注</span><span class="sxs-lookup"><span data-stu-id="47427-114">Remarks</span></span>  
 <span data-ttu-id="47427-115">`DefineScope`创建一组的内存中元数据表、 生成元数据，一个唯一 GUID （模块版本标识符或 MVID） 并在模块表中为发出编译单元中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="47427-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="47427-116">你可以将属性附加到元数据范围作为一个整体通过[imetadataemit:: Setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)或[imetadataemit:: Definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)方法，根据需要。</span><span class="sxs-lookup"><span data-stu-id="47427-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47427-117">惠?</span><span class="sxs-lookup"><span data-stu-id="47427-117">Requirements</span></span>  
 <span data-ttu-id="47427-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47427-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47427-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47427-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47427-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="47427-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47427-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47427-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47427-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="47427-122">See Also</span></span>  
 [<span data-ttu-id="47427-123">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="47427-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="47427-124">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="47427-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="47427-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="47427-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="47427-126">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="47427-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="47427-127">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="47427-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
