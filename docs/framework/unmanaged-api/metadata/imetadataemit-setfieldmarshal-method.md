---
title: IMetaDataEmit::SetFieldMarshal 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: cdbcdb9359d295ad9bed2050ed36499feba74d9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442272"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="338ad-102">IMetaDataEmit::SetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="338ad-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="338ad-103">为指定的标记引用的字段、方法返回或方法参数设置 PInvoke 封送处理信息。</span><span class="sxs-lookup"><span data-stu-id="338ad-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="338ad-104">语法</span><span class="sxs-lookup"><span data-stu-id="338ad-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="338ad-105">参数</span><span class="sxs-lookup"><span data-stu-id="338ad-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="338ad-106">中目标数据项的标记。</span><span class="sxs-lookup"><span data-stu-id="338ad-106">[in] The token for target data item.</span></span> <span data-ttu-id="338ad-107">这是 `mdFieldDef` 或 `mdParamDef` 令牌。</span><span class="sxs-lookup"><span data-stu-id="338ad-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="338ad-108">中非托管类型的签名。</span><span class="sxs-lookup"><span data-stu-id="338ad-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="338ad-109">中`pvNativeType`中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="338ad-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="338ad-110">要求</span><span class="sxs-lookup"><span data-stu-id="338ad-110">Requirements</span></span>  
 <span data-ttu-id="338ad-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="338ad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="338ad-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="338ad-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="338ad-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="338ad-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="338ad-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="338ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338ad-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="338ad-115">See also</span></span>

- [<span data-ttu-id="338ad-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="338ad-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="338ad-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="338ad-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
