---
title: IMetaDataEmit::DefineUserString 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f24dd3864be1bda454ac5e863f3fa2caf736bda9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050111"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="e824c-102">IMetaDataEmit::DefineUserString 方法</span><span class="sxs-lookup"><span data-stu-id="e824c-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="e824c-103">获取指定文本字符串的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="e824c-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e824c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e824c-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e824c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e824c-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="e824c-106">[in]要存储的用户字符串。</span><span class="sxs-lookup"><span data-stu-id="e824c-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="e824c-107">[in]中的宽字符计数`szString`。</span><span class="sxs-lookup"><span data-stu-id="e824c-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="e824c-108">[out]分配的字符串标记。</span><span class="sxs-lookup"><span data-stu-id="e824c-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e824c-109">要求</span><span class="sxs-lookup"><span data-stu-id="e824c-109">Requirements</span></span>  
 <span data-ttu-id="e824c-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e824c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e824c-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e824c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e824c-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e824c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e824c-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e824c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e824c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e824c-114">See also</span></span>

- [<span data-ttu-id="e824c-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="e824c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e824c-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="e824c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
