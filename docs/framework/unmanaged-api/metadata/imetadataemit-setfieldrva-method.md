---
title: IMetaDataEmit::SetFieldRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfc4ac58785b766e74d836fa3cf3b1aca75f01d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521018"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="e5a35-102">IMetaDataEmit::SetFieldRVA 方法</span><span class="sxs-lookup"><span data-stu-id="e5a35-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="e5a35-103">设置指定标记所引用的字段的相对虚拟地址的全局变量值。</span><span class="sxs-lookup"><span data-stu-id="e5a35-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a35-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5a35-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5a35-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5a35-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="e5a35-106">[in]目标字段的标记。</span><span class="sxs-lookup"><span data-stu-id="e5a35-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="e5a35-107">[in]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="e5a35-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a35-108">要求</span><span class="sxs-lookup"><span data-stu-id="e5a35-108">Requirements</span></span>  
 <span data-ttu-id="e5a35-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a35-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a35-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5a35-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5a35-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e5a35-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5a35-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a35-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a35-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a35-113">See also</span></span>
- [<span data-ttu-id="e5a35-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="e5a35-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e5a35-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="e5a35-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
