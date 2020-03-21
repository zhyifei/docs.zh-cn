---
title: IMetaDataImport2::EnumMethodSpecs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177175"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="dfc30-102">IMetaDataImport2::EnumMethodSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="dfc30-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="dfc30-103">获取与指定方法Def或会员Ref令牌关联的 MethodSpec 令牌数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="dfc30-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc30-104">语法</span><span class="sxs-lookup"><span data-stu-id="dfc30-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="dfc30-105">parameters</span><span class="sxs-lookup"><span data-stu-id="dfc30-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="dfc30-106">[进出]指向 的枚举器的`rMethodSpecs`指针。</span><span class="sxs-lookup"><span data-stu-id="dfc30-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="dfc30-107">[在]代表其方法Spec令牌的方法的会员Ref或 MethodDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="dfc30-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="dfc30-108">如果 值`tk`为 0（零），则将枚举作用域中的所有 MethodSpec 令牌。</span><span class="sxs-lookup"><span data-stu-id="dfc30-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="dfc30-109">[出]要枚举的 MethodSpec 令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="dfc30-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dfc30-110">[在]要放置在 中`rMethodSpecs`的最大令牌数。</span><span class="sxs-lookup"><span data-stu-id="dfc30-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="dfc30-111">[出]放置在 的`rMethodSpecs`返回的令牌数。</span><span class="sxs-lookup"><span data-stu-id="dfc30-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfc30-112">返回值</span><span class="sxs-lookup"><span data-stu-id="dfc30-112">Return Value</span></span>  
  
|<span data-ttu-id="dfc30-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dfc30-113">HRESULT</span></span>|<span data-ttu-id="dfc30-114">说明</span><span class="sxs-lookup"><span data-stu-id="dfc30-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="dfc30-115">`EnumMethodSpecs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="dfc30-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="dfc30-116">`phEnum`没有成员元素。</span><span class="sxs-lookup"><span data-stu-id="dfc30-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="dfc30-117">在这种情况下，`pcMethodSpecs`设置为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="dfc30-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfc30-118">要求</span><span class="sxs-lookup"><span data-stu-id="dfc30-118">Requirements</span></span>  
 <span data-ttu-id="dfc30-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dfc30-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfc30-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="dfc30-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dfc30-121">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dfc30-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dfc30-122">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc30-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc30-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfc30-123">See also</span></span>

- [<span data-ttu-id="dfc30-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="dfc30-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="dfc30-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="dfc30-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
