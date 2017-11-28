---
title: "IMetaDataEmit::SaveToMemory 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SaveToMemory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 685ed69964970f505ad6f938af361c48664d2279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="cdca6-102">IMetaDataEmit::SaveToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="cdca6-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="cdca6-103">将所有元数据保存到指定的内存区域的当前作用域中。</span><span class="sxs-lookup"><span data-stu-id="cdca6-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdca6-104">语法</span><span class="sxs-lookup"><span data-stu-id="cdca6-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdca6-105">参数</span><span class="sxs-lookup"><span data-stu-id="cdca6-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="cdca6-106">[out]从此处开始写入元数据地址。</span><span class="sxs-lookup"><span data-stu-id="cdca6-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="cdca6-107">[in]以字节为单位分配的内存大小。</span><span class="sxs-lookup"><span data-stu-id="cdca6-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdca6-108">要求</span><span class="sxs-lookup"><span data-stu-id="cdca6-108">Requirements</span></span>  
 <span data-ttu-id="cdca6-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cdca6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdca6-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cdca6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cdca6-111">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cdca6-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdca6-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdca6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdca6-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdca6-113">See Also</span></span>  
 [<span data-ttu-id="cdca6-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="cdca6-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="cdca6-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="cdca6-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
