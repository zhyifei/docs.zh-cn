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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa95a737747e9153eb844cddd8e0684585b9108b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049968"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="865ed-102">IMetaDataEmit2::SaveDeltaToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="865ed-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="865ed-103">将更改从当前会话中编辑和继续保存到内存中。</span><span class="sxs-lookup"><span data-stu-id="865ed-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="865ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="865ed-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="865ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="865ed-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="865ed-106">[out]开始写入的元数据增量的地址。</span><span class="sxs-lookup"><span data-stu-id="865ed-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="865ed-107">[in]所做的更改的大小。</span><span class="sxs-lookup"><span data-stu-id="865ed-107">[in] The size of the changes.</span></span> <span data-ttu-id="865ed-108">使用[IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)确定的大小。</span><span class="sxs-lookup"><span data-stu-id="865ed-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="865ed-109">要求</span><span class="sxs-lookup"><span data-stu-id="865ed-109">Requirements</span></span>  
 <span data-ttu-id="865ed-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="865ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="865ed-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="865ed-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="865ed-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="865ed-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="865ed-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="865ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="865ed-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="865ed-114">See also</span></span>

- [<span data-ttu-id="865ed-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="865ed-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="865ed-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="865ed-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
