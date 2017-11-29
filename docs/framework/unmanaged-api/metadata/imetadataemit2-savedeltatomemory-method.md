---
title: "IMetaDataEmit2::SaveDeltaToMemory 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDeltaToMemory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8c3148cdb417d627afd9ba007fb9892b47dcef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="88880-102">IMetaDataEmit2::SaveDeltaToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="88880-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="88880-103">将更改从当前的编辑并继续会话保存到内存中。</span><span class="sxs-lookup"><span data-stu-id="88880-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88880-104">语法</span><span class="sxs-lookup"><span data-stu-id="88880-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88880-105">参数</span><span class="sxs-lookup"><span data-stu-id="88880-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="88880-106">[out]从此处开始写入的元数据增量地址。</span><span class="sxs-lookup"><span data-stu-id="88880-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="88880-107">[in]所做的更改的大小。</span><span class="sxs-lookup"><span data-stu-id="88880-107">[in] The size of the changes.</span></span> <span data-ttu-id="88880-108">使用[imetadataemit2:: Getdeltasavesize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)来确定的大小。</span><span class="sxs-lookup"><span data-stu-id="88880-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88880-109">要求</span><span class="sxs-lookup"><span data-stu-id="88880-109">Requirements</span></span>  
 <span data-ttu-id="88880-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88880-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88880-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88880-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88880-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="88880-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88880-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88880-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88880-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88880-114">See Also</span></span>  
 [<span data-ttu-id="88880-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="88880-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="88880-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="88880-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
