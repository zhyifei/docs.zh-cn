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
ms.openlocfilehash: be4fb0b4b49408a97b318e0f54f5a753f3f24ef1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435800"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="5f762-102">IMetaDataEmit::SaveToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="5f762-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="5f762-103">将当前范围中的所有元数据保存到指定的内存区域。</span><span class="sxs-lookup"><span data-stu-id="5f762-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f762-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f762-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f762-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f762-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="5f762-106">弄开始写入元数据的地址。</span><span class="sxs-lookup"><span data-stu-id="5f762-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="5f762-107">中已分配内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5f762-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f762-108">要求</span><span class="sxs-lookup"><span data-stu-id="5f762-108">Requirements</span></span>  
 <span data-ttu-id="5f762-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f762-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f762-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5f762-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f762-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5f762-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f762-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f762-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f762-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f762-113">See also</span></span>

- [<span data-ttu-id="5f762-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5f762-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5f762-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5f762-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
