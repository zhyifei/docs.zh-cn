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
ms.openlocfilehash: 7648a1b3d219ee5d2b1ddc6b26f7b65c9ac85105
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175637"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="916bb-102">IMetaDataEmit::SetFieldRVA 方法</span><span class="sxs-lookup"><span data-stu-id="916bb-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="916bb-103">为指定令牌引用的字段的相对虚拟地址设置全局变量值。</span><span class="sxs-lookup"><span data-stu-id="916bb-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="916bb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="916bb-105">parameters</span><span class="sxs-lookup"><span data-stu-id="916bb-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="916bb-106">[在]目标字段的令牌。</span><span class="sxs-lookup"><span data-stu-id="916bb-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="916bb-107">[在]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="916bb-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="916bb-108">要求</span><span class="sxs-lookup"><span data-stu-id="916bb-108">Requirements</span></span>  
 <span data-ttu-id="916bb-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="916bb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="916bb-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="916bb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="916bb-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="916bb-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="916bb-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="916bb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916bb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="916bb-113">See also</span></span>

- [<span data-ttu-id="916bb-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="916bb-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="916bb-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="916bb-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
