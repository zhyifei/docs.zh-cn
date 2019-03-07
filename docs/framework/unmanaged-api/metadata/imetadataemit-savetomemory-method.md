---
title: IMetaDataEmit::SaveToMemory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6e9bb51965b258093321a5dbb19447ec6d6474d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471807"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="91a77-102">IMetaDataEmit::SaveToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="91a77-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="91a77-103">将保存到指定的内存区域的当前作用域中的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="91a77-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a77-104">语法</span><span class="sxs-lookup"><span data-stu-id="91a77-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91a77-105">参数</span><span class="sxs-lookup"><span data-stu-id="91a77-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="91a77-106">[out]要开始编写元数据地址。</span><span class="sxs-lookup"><span data-stu-id="91a77-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="91a77-107">[in]以字节为单位分配的内存大小。</span><span class="sxs-lookup"><span data-stu-id="91a77-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a77-108">要求</span><span class="sxs-lookup"><span data-stu-id="91a77-108">Requirements</span></span>  
 <span data-ttu-id="91a77-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91a77-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a77-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="91a77-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91a77-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="91a77-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91a77-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a77-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a77-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="91a77-113">See also</span></span>
- [<span data-ttu-id="91a77-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="91a77-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="91a77-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="91a77-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
