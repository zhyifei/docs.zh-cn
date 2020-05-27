---
title: IMetaDataEmit::GetTokenFromTypeSpec 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 1cd09fe785bb37c892417ddbf1efaaaa90e121bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009231"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="d3352-102">IMetaDataEmit::GetTokenFromTypeSpec 方法</span><span class="sxs-lookup"><span data-stu-id="d3352-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="d3352-103">获取具有指定元数据签名的类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d3352-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3352-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3352-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3352-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3352-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="d3352-106">中要定义的签名。</span><span class="sxs-lookup"><span data-stu-id="d3352-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="d3352-107">中中的字节数 `pvSig` 。</span><span class="sxs-lookup"><span data-stu-id="d3352-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="d3352-108">弄`mdTypeSpec`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="d3352-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3352-109">要求</span><span class="sxs-lookup"><span data-stu-id="d3352-109">Requirements</span></span>  
 <span data-ttu-id="d3352-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3352-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3352-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="d3352-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3352-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d3352-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3352-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3352-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3352-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3352-114">See also</span></span>

- [<span data-ttu-id="d3352-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d3352-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d3352-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="d3352-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
