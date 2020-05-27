---
title: IMetaDataEmit::DefineCustomAttribute 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 17757df566ba8d141e7adec00dcc1f75959d0e00
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005619"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="21820-102">IMetaDataEmit::DefineCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="21820-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="21820-103">使用指定的元数据签名创建要附加到指定对象的自定义属性的定义，并获取该自定义属性定义的标记。</span><span class="sxs-lookup"><span data-stu-id="21820-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21820-104">语法</span><span class="sxs-lookup"><span data-stu-id="21820-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21820-105">参数</span><span class="sxs-lookup"><span data-stu-id="21820-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="21820-106">中所有者项的标记。</span><span class="sxs-lookup"><span data-stu-id="21820-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="21820-107">中标识自定义属性的标记。</span><span class="sxs-lookup"><span data-stu-id="21820-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="21820-108">中指向自定义属性的指针。</span><span class="sxs-lookup"><span data-stu-id="21820-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="21820-109">中中的字节数 `pCustomAttribute` 。</span><span class="sxs-lookup"><span data-stu-id="21820-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="21820-110">弄`mdCustomAttribute`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="21820-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21820-111">要求</span><span class="sxs-lookup"><span data-stu-id="21820-111">Requirements</span></span>  
 <span data-ttu-id="21820-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21820-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21820-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="21820-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21820-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="21820-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21820-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21820-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21820-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21820-116">See also</span></span>

- [<span data-ttu-id="21820-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="21820-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="21820-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="21820-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
