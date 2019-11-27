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
ms.openlocfilehash: b8755629cca27784609de8166dddf44ed1c82bdc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432533"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="c068d-102">IMetaDataEmit::SetMethodImplFlags 方法</span><span class="sxs-lookup"><span data-stu-id="c068d-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="c068d-103">设置或更新指定的标记所引用的继承方法实现的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="c068d-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c068d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c068d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c068d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c068d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="c068d-106">中要更改的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="c068d-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="c068d-107">中用于指定方法实现功能的[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举值的组合。</span><span class="sxs-lookup"><span data-stu-id="c068d-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c068d-108">要求</span><span class="sxs-lookup"><span data-stu-id="c068d-108">Requirements</span></span>  
 <span data-ttu-id="c068d-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c068d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c068d-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c068d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c068d-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c068d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c068d-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c068d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c068d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c068d-113">See also</span></span>

- [<span data-ttu-id="c068d-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="c068d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c068d-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="c068d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
