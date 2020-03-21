---
title: IMetaDataEmit2::SaveDeltaToMemory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: 5ec4fe2a8e949cf6e9aa0ce68f4d4e49b72170b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177433"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="05e48-102">IMetaDataEmit2::SaveDeltaToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="05e48-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="05e48-103">将更改从当前编辑和继续会话保存到内存。</span><span class="sxs-lookup"><span data-stu-id="05e48-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e48-104">语法</span><span class="sxs-lookup"><span data-stu-id="05e48-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05e48-105">parameters</span><span class="sxs-lookup"><span data-stu-id="05e48-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="05e48-106">[出]开始写入元数据增量的地址。</span><span class="sxs-lookup"><span data-stu-id="05e48-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="05e48-107">[在]更改的大小。</span><span class="sxs-lookup"><span data-stu-id="05e48-107">[in] The size of the changes.</span></span> <span data-ttu-id="05e48-108">使用[IMetaDataEmit2：：获取增量保存大小](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)以确定大小。</span><span class="sxs-lookup"><span data-stu-id="05e48-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05e48-109">要求</span><span class="sxs-lookup"><span data-stu-id="05e48-109">Requirements</span></span>  
 <span data-ttu-id="05e48-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05e48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e48-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="05e48-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05e48-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="05e48-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05e48-113">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e48-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e48-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05e48-114">See also</span></span>

- [<span data-ttu-id="05e48-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="05e48-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="05e48-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="05e48-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
