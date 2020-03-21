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
ms.openlocfilehash: d8843b2b5f69696dc206e9b530e3062ff225e89e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177585"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="66d08-102">IMetaDataEmit::SaveToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="66d08-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="66d08-103">将当前作用域中的所有元数据保存到指定的内存区域。</span><span class="sxs-lookup"><span data-stu-id="66d08-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d08-104">语法</span><span class="sxs-lookup"><span data-stu-id="66d08-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66d08-105">parameters</span><span class="sxs-lookup"><span data-stu-id="66d08-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="66d08-106">[出]开始写入元数据的地址。</span><span class="sxs-lookup"><span data-stu-id="66d08-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="66d08-107">[在]已分配内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="66d08-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d08-108">要求</span><span class="sxs-lookup"><span data-stu-id="66d08-108">Requirements</span></span>  
 <span data-ttu-id="66d08-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66d08-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d08-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="66d08-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66d08-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="66d08-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66d08-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d08-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d08-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66d08-113">See also</span></span>

- [<span data-ttu-id="66d08-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="66d08-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="66d08-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="66d08-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
