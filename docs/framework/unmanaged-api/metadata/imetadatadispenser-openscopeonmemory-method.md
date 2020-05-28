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
ms.openlocfilehash: 69e5e05012d2b44a76a986591ec990f66bf8ae20
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007320"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="a3496-102">IMetaDataDispenser::OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="a3496-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="a3496-103">打开包含现有元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="a3496-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="a3496-104">也就是说，此方法将打开一个指定的内存区域，其中的现有数据将被视为元数据。</span><span class="sxs-lookup"><span data-stu-id="a3496-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3496-105">语法</span><span class="sxs-lookup"><span data-stu-id="a3496-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3496-106">参数</span><span class="sxs-lookup"><span data-stu-id="a3496-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="a3496-107">中指定内存区域起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a3496-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="a3496-108">中内存区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a3496-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a3496-109">中[CorOpenFlags](coropenflags-enumeration.md)枚举的值，该值指定用于打开的模式（读取、写入等）。</span><span class="sxs-lookup"><span data-stu-id="a3496-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="a3496-110">中要返回的所需元数据接口的 IID;调用方将使用接口导入（读取）或发出（写入）元数据。</span><span class="sxs-lookup"><span data-stu-id="a3496-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="a3496-111">的值 `riid` 必须指定一个 "导入" 或 "发出" 接口。</span><span class="sxs-lookup"><span data-stu-id="a3496-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="a3496-112">有效值为 IID_IMetaDataEmit、IID_IMetaDataImport、IID_IMetaDataAssemblyEmit、IID_IMetaDataAssemblyImport、IID_IMetaDataEmit2 或 IID_IMetaDataImport2。</span><span class="sxs-lookup"><span data-stu-id="a3496-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a3496-113">弄指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a3496-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3496-114">备注</span><span class="sxs-lookup"><span data-stu-id="a3496-114">Remarks</span></span>  
 <span data-ttu-id="a3496-115">可以使用 "导入" 接口中的方法查询元数据的内存中副本，或使用 "发出" 接口之一中的方法将其添加到中。</span><span class="sxs-lookup"><span data-stu-id="a3496-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="a3496-116">`OpenScopeOnMemory`方法类似于[IMetaDataDispenser：： OpenScope](imetadatadispenser-openscope-method.md)方法，不同之处在于相关元数据已存在于内存中，而不是位于磁盘上的文件中。</span><span class="sxs-lookup"><span data-stu-id="a3496-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="a3496-117">如果内存的目标区域不包含公共语言运行时（CLR）元数据，则该 `OpenScopeOnMemory` 方法将失败。</span><span class="sxs-lookup"><span data-stu-id="a3496-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3496-118">要求</span><span class="sxs-lookup"><span data-stu-id="a3496-118">Requirements</span></span>  
 <span data-ttu-id="a3496-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3496-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3496-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a3496-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3496-121">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a3496-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3496-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3496-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3496-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3496-123">See also</span></span>

- [<span data-ttu-id="a3496-124">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="a3496-125">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="a3496-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="a3496-127">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="a3496-128">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a3496-129">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="a3496-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a3496-131">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a3496-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
