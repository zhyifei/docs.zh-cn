---
title: IMetaDataEmit::SetRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: fe0b4b7fef0d05c4acc06dad5bc8a4eaf0722c9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175572"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="b1693-102">IMetaDataEmit::SetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="b1693-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="b1693-103">设置指定方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="b1693-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1693-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1693-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1693-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b1693-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="b1693-106">[在]目标方法或方法实现的令牌。</span><span class="sxs-lookup"><span data-stu-id="b1693-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="b1693-107">[在]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="b1693-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1693-108">要求</span><span class="sxs-lookup"><span data-stu-id="b1693-108">Requirements</span></span>  
 <span data-ttu-id="b1693-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1693-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1693-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="b1693-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1693-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b1693-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1693-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1693-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1693-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1693-113">See also</span></span>

- [<span data-ttu-id="b1693-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="b1693-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b1693-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="b1693-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
