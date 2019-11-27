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
ms.openlocfilehash: 577a4f6bb8315cfb1cb462703dd0cb9b23b60704
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434055"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="71abe-102">IMetaDataTables::GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="71abe-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="71abe-103">获取一个指针，该指针指向与指定的行索引相关联的标记的数组。</span><span class="sxs-lookup"><span data-stu-id="71abe-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71abe-104">语法</span><span class="sxs-lookup"><span data-stu-id="71abe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71abe-105">参数</span><span class="sxs-lookup"><span data-stu-id="71abe-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="71abe-106">中要返回的编码标记的类型。</span><span class="sxs-lookup"><span data-stu-id="71abe-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="71abe-107">弄指向 `ppTokens`长度的指针。</span><span class="sxs-lookup"><span data-stu-id="71abe-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="71abe-108">弄指向数组的指针的指针，该数组包含返回的标记的列表。</span><span class="sxs-lookup"><span data-stu-id="71abe-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="71abe-109">弄指向指向 `ixCdTkn`的令牌名称的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="71abe-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71abe-110">要求</span><span class="sxs-lookup"><span data-stu-id="71abe-110">Requirements</span></span>  
 <span data-ttu-id="71abe-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71abe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71abe-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="71abe-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71abe-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71abe-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71abe-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71abe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71abe-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71abe-115">See also</span></span>

- [<span data-ttu-id="71abe-116">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="71abe-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="71abe-117">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="71abe-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
