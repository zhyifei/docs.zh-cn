---
title: IMetaDataDispenser::OpenScope 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175936"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="593af-102">IMetaDataDispenser::OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="593af-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="593af-103">打开现有的磁盘文件并将其元数据映射到内存中。</span><span class="sxs-lookup"><span data-stu-id="593af-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="593af-104">语法</span><span class="sxs-lookup"><span data-stu-id="593af-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="593af-105">parameters</span><span class="sxs-lookup"><span data-stu-id="593af-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="593af-106">[在]要打开的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="593af-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="593af-107">该文件必须包含通用语言运行时 （CLR） 元数据。</span><span class="sxs-lookup"><span data-stu-id="593af-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="593af-108">[在][CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举的值，用于指定打开的模式（读取、写入等）。</span><span class="sxs-lookup"><span data-stu-id="593af-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="593af-109">[在]要返回的所需元数据接口的 IID;调用方将使用接口导入（读取）或发出（写入）元数据。</span><span class="sxs-lookup"><span data-stu-id="593af-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="593af-110">的值`riid`必须指定其中一个"导入"或"发射"接口。</span><span class="sxs-lookup"><span data-stu-id="593af-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="593af-111">有效值IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2或IID_IMetaDataImport2。</span><span class="sxs-lookup"><span data-stu-id="593af-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="593af-112">[出]指向返回接口的指针。</span><span class="sxs-lookup"><span data-stu-id="593af-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="593af-113">备注</span><span class="sxs-lookup"><span data-stu-id="593af-113">Remarks</span></span>  
 <span data-ttu-id="593af-114">可以使用"导入"接口之一的方法查询元数据的内存副本，也可以添加到使用"emit"接口之一的方法。</span><span class="sxs-lookup"><span data-stu-id="593af-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="593af-115">如果目标文件不包含 CLR 元数据，则`OpenScope`该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="593af-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="593af-116">在 .NET 框架版本 1.0 和版本 1.1 中，`dwOpenFlags`如果使用设置为 Read 打开作用域，则它有资格共享。</span><span class="sxs-lookup"><span data-stu-id="593af-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="593af-117">也就是说，如果后续调用以`OpenScope`以前打开的文件的名称传递，则重用现有作用域，并且不会创建新的数据结构集。</span><span class="sxs-lookup"><span data-stu-id="593af-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="593af-118">但是，由于这种共享，可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="593af-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="593af-119">在 .NET 框架版本 2.0 中，`dwOpenFlags`不再共享使用设置为 Read 打开的作用域。</span><span class="sxs-lookup"><span data-stu-id="593af-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="593af-120">使用 ReadOnly 值允许共享作用域。</span><span class="sxs-lookup"><span data-stu-id="593af-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="593af-121">共享作用域时，使用"读/写"元数据接口的查询将失败。</span><span class="sxs-lookup"><span data-stu-id="593af-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="593af-122">要求</span><span class="sxs-lookup"><span data-stu-id="593af-122">Requirements</span></span>  
 <span data-ttu-id="593af-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="593af-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="593af-124">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="593af-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="593af-125">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="593af-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="593af-126">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="593af-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593af-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="593af-127">See also</span></span>

- [<span data-ttu-id="593af-128">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="593af-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="593af-129">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="593af-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="593af-130">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="593af-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="593af-131">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="593af-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="593af-132">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="593af-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="593af-133">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="593af-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="593af-134">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="593af-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="593af-135">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="593af-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
