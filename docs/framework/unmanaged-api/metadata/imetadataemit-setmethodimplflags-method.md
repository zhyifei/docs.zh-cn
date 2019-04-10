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
ms.openlocfilehash: 28c0aa37bdcae2a09a4d53f920efd3ffe7117bd3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145166"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="3731d-102">IMetaDataEmit::SetMethodImplFlags 方法</span><span class="sxs-lookup"><span data-stu-id="3731d-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="3731d-103">设置或更新指定的标记所引用的继承的方法实现的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="3731d-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3731d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3731d-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3731d-105">参数</span><span class="sxs-lookup"><span data-stu-id="3731d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="3731d-106">[in]若要更改方法的标记。</span><span class="sxs-lookup"><span data-stu-id="3731d-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="3731d-107">[in]值的组合[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举，用于指定方法实现功能。</span><span class="sxs-lookup"><span data-stu-id="3731d-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3731d-108">要求</span><span class="sxs-lookup"><span data-stu-id="3731d-108">Requirements</span></span>  
 <span data-ttu-id="3731d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3731d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3731d-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3731d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3731d-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3731d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3731d-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3731d-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3731d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3731d-113">See also</span></span>

- [<span data-ttu-id="3731d-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="3731d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3731d-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="3731d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
