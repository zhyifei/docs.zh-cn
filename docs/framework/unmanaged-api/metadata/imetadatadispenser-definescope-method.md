---
title: IMetaDataDispenser::DefineScope 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177645"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="02a7a-102">IMetaDataDispenser::DefineScope 方法</span><span class="sxs-lookup"><span data-stu-id="02a7a-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="02a7a-103">在内存中创建一个新区域，您可以在其中创建新元数据。</span><span class="sxs-lookup"><span data-stu-id="02a7a-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a7a-104">语法</span><span class="sxs-lookup"><span data-stu-id="02a7a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a7a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="02a7a-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="02a7a-106">[在]要创建的元数据结构版本的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="02a7a-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="02a7a-107">此值必须CLSID_CorMetaDataRuntime .NET 框架版本 2.0。</span><span class="sxs-lookup"><span data-stu-id="02a7a-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="02a7a-108">[在]指定选项的标志。</span><span class="sxs-lookup"><span data-stu-id="02a7a-108">[in] Flags that specify options.</span></span> <span data-ttu-id="02a7a-109">此值对于 .NET 框架 2.0 必须为零。</span><span class="sxs-lookup"><span data-stu-id="02a7a-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="02a7a-110">[在]要返回的所需元数据接口的 IID;调用方将使用接口创建新元数据。</span><span class="sxs-lookup"><span data-stu-id="02a7a-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="02a7a-111">的值`riid`必须指定其中一个"emit"接口。</span><span class="sxs-lookup"><span data-stu-id="02a7a-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="02a7a-112">有效值IID_IMetaDataEmit、IID_IMetaDataAssemblyEmit 或IID_IMetaDataEmit2。</span><span class="sxs-lookup"><span data-stu-id="02a7a-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="02a7a-113">[出]指向返回接口的指针。</span><span class="sxs-lookup"><span data-stu-id="02a7a-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a7a-114">备注</span><span class="sxs-lookup"><span data-stu-id="02a7a-114">Remarks</span></span>  
 <span data-ttu-id="02a7a-115">`DefineScope`创建一组内存中元数据表，为元数据生成唯一 GUID（模块版本标识符或 MVID），并在模块表中为发出的编译单元创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="02a7a-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="02a7a-116">您可以根据需要使用[IMetaDataEmit：setModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)或[IMetaDataEmit：:DefineCustom属性](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)方法将属性附加到整个元数据范围。</span><span class="sxs-lookup"><span data-stu-id="02a7a-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a7a-117">要求</span><span class="sxs-lookup"><span data-stu-id="02a7a-117">Requirements</span></span>  
 <span data-ttu-id="02a7a-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02a7a-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a7a-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="02a7a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02a7a-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="02a7a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02a7a-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a7a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a7a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02a7a-122">See also</span></span>

- [<span data-ttu-id="02a7a-123">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="02a7a-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="02a7a-124">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="02a7a-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="02a7a-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="02a7a-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="02a7a-126">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="02a7a-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="02a7a-127">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="02a7a-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
