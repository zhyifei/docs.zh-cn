---
title: IMetaDataTables::GetCodedTokenInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a9eb51643271fd27a6d4795fc1729766b44b239
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468788"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="2b654-102">IMetaDataTables::GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="2b654-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="2b654-103">获取与指定的行索引相关联的标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="2b654-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b654-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b654-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b654-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b654-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="2b654-106">[in]编码的令牌要返回的类型。</span><span class="sxs-lookup"><span data-stu-id="2b654-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2b654-107">[out]长度的指针`ppTokens`。</span><span class="sxs-lookup"><span data-stu-id="2b654-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="2b654-108">[out]指向包含返回令牌的列表的数组的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="2b654-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="2b654-109">[out]指针到指向在令牌的名称`ixCdTkn`。</span><span class="sxs-lookup"><span data-stu-id="2b654-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b654-110">要求</span><span class="sxs-lookup"><span data-stu-id="2b654-110">Requirements</span></span>  
 <span data-ttu-id="2b654-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b654-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b654-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b654-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b654-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2b654-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b654-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b654-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b654-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b654-115">See also</span></span>
- [<span data-ttu-id="2b654-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="2b654-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2b654-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="2b654-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
