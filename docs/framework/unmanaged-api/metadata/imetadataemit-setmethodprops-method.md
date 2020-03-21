---
title: IMetaDataEmit::SetMethodProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 9662a14b4ea97aed16968083489324d46c38dda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177515"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="5fa3d-102">IMetaDataEmit::SetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="5fa3d-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="5fa3d-103">设置或更新由之前调用[IMetaDataEmit：:DefineMethod）](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)定义的方法的要素（存储在指定的相对虚拟地址）</span><span class="sxs-lookup"><span data-stu-id="5fa3d-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5fa3d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa3d-105">parameters</span><span class="sxs-lookup"><span data-stu-id="5fa3d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="5fa3d-106">[在]要更改的方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="5fa3d-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="5fa3d-107">[在]成员属性。</span><span class="sxs-lookup"><span data-stu-id="5fa3d-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="5fa3d-108">[在]代码的地址。</span><span class="sxs-lookup"><span data-stu-id="5fa3d-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="5fa3d-109">[在]方法的实现标志。</span><span class="sxs-lookup"><span data-stu-id="5fa3d-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa3d-110">要求</span><span class="sxs-lookup"><span data-stu-id="5fa3d-110">Requirements</span></span>  
 <span data-ttu-id="5fa3d-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa3d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa3d-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5fa3d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5fa3d-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5fa3d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fa3d-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa3d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa3d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa3d-115">See also</span></span>

- [<span data-ttu-id="5fa3d-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5fa3d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5fa3d-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5fa3d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
