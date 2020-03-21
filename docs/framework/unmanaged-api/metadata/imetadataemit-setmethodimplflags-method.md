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
ms.openlocfilehash: 7ed7770f26ea4620d79f3be3f67e72f73c75057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175624"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="9173d-102">IMetaDataEmit::SetMethodImplFlags 方法</span><span class="sxs-lookup"><span data-stu-id="9173d-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="9173d-103">设置或更新指定令牌引用的继承方法实现的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="9173d-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9173d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9173d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9173d-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9173d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="9173d-106">[在]要更改的方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="9173d-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="9173d-107">[在][CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举的值的组合，用于指定方法实现要素。</span><span class="sxs-lookup"><span data-stu-id="9173d-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9173d-108">要求</span><span class="sxs-lookup"><span data-stu-id="9173d-108">Requirements</span></span>  
 <span data-ttu-id="9173d-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9173d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9173d-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="9173d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9173d-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9173d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9173d-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9173d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9173d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9173d-113">See also</span></span>

- [<span data-ttu-id="9173d-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="9173d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9173d-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="9173d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
