---
title: IMetaDataEmit::SetMethodImplFlags 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a437ff11114ea8d577b2fc3b81cd981cebb8c8d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751064"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="d0937-102">IMetaDataEmit::SetMethodImplFlags 方法</span><span class="sxs-lookup"><span data-stu-id="d0937-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="d0937-103">设置或更新指定的标记所引用的继承的方法实现的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="d0937-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0937-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0937-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0937-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0937-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="d0937-106">[in]若要更改方法的标记。</span><span class="sxs-lookup"><span data-stu-id="d0937-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="d0937-107">[in]值的组合[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举，用于指定方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="d0937-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0937-108">要求</span><span class="sxs-lookup"><span data-stu-id="d0937-108">Requirements</span></span>  
 <span data-ttu-id="d0937-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0937-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0937-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0937-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0937-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d0937-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0937-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0937-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0937-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0937-113">See also</span></span>

- [<span data-ttu-id="d0937-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d0937-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d0937-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d0937-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
