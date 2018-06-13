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
ms.openlocfilehash: b680e807554a60711e61729680e9c9fcf1c8fdaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446174"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="77357-102">IMetaDataEmit::SaveToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="77357-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="77357-103">将所有元数据保存到指定的内存区域的当前作用域中。</span><span class="sxs-lookup"><span data-stu-id="77357-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77357-104">语法</span><span class="sxs-lookup"><span data-stu-id="77357-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77357-105">参数</span><span class="sxs-lookup"><span data-stu-id="77357-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="77357-106">[out]从此处开始写入元数据地址。</span><span class="sxs-lookup"><span data-stu-id="77357-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="77357-107">[in]以字节为单位分配的内存大小。</span><span class="sxs-lookup"><span data-stu-id="77357-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77357-108">要求</span><span class="sxs-lookup"><span data-stu-id="77357-108">Requirements</span></span>  
 <span data-ttu-id="77357-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77357-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77357-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77357-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77357-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77357-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77357-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77357-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77357-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="77357-113">See Also</span></span>  
 [<span data-ttu-id="77357-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="77357-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="77357-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="77357-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
