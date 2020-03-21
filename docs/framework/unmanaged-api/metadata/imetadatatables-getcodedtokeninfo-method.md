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
ms.openlocfilehash: 64c70fe0b657047ae35dccb763fa57120403deef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177154"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="8a389-102">IMetaDataTables::GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="8a389-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="8a389-103">获取指向与指定行索引关联的令牌数组的指针。</span><span class="sxs-lookup"><span data-stu-id="8a389-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a389-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a389-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a389-105">parameters</span><span class="sxs-lookup"><span data-stu-id="8a389-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="8a389-106">[在]要返回的编码令牌类型。</span><span class="sxs-lookup"><span data-stu-id="8a389-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8a389-107">[出]指向 长度的`ppTokens`指针。</span><span class="sxs-lookup"><span data-stu-id="8a389-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="8a389-108">[出]指向包含返回令牌列表的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="8a389-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="8a389-109">[出]指向 的`ixCdTkn`标记名称的指针。</span><span class="sxs-lookup"><span data-stu-id="8a389-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a389-110">要求</span><span class="sxs-lookup"><span data-stu-id="8a389-110">Requirements</span></span>  
 <span data-ttu-id="8a389-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a389-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a389-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="8a389-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a389-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8a389-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a389-114">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a389-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a389-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a389-115">See also</span></span>

- [<span data-ttu-id="8a389-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="8a389-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8a389-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="8a389-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
