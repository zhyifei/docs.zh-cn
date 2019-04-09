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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3641fcda33a497293dbf87b419c8606847dc296
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130944"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="654cf-102">IMetaDataImport2::EnumMethodSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="654cf-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="654cf-103">获取可枚举数组 MethodSpec 与关联的标记指定的 MethodDef 或 MemberRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="654cf-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="654cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="654cf-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="654cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="654cf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="654cf-106">[in、 out]指向的枚举器的`rMethodSpecs`。</span><span class="sxs-lookup"><span data-stu-id="654cf-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="654cf-107">[in]新对象或 MemberRef 令牌，表示其 MethodSpec 令牌是要枚举的方法。</span><span class="sxs-lookup"><span data-stu-id="654cf-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="654cf-108">如果的值`tk`为 0 （零），则将枚举所有 MethodSpec 令牌的作用域中。</span><span class="sxs-lookup"><span data-stu-id="654cf-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="654cf-109">[out]要枚举的 MethodSpec 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="654cf-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="654cf-110">[in]要放置在中的令牌的请求最大数目`rMethodSpecs`。</span><span class="sxs-lookup"><span data-stu-id="654cf-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="654cf-111">[out]返回的标记数置于`rMethodSpecs`。</span><span class="sxs-lookup"><span data-stu-id="654cf-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="654cf-112">返回值</span><span class="sxs-lookup"><span data-stu-id="654cf-112">Return Value</span></span>  
  
|<span data-ttu-id="654cf-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="654cf-113">HRESULT</span></span>|<span data-ttu-id="654cf-114">描述</span><span class="sxs-lookup"><span data-stu-id="654cf-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` <span data-ttu-id="654cf-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="654cf-115">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="654cf-116">不包含任何成员元素。</span><span class="sxs-lookup"><span data-stu-id="654cf-116">has no member elements.</span></span> <span data-ttu-id="654cf-117">在这种情况下，`pcMethodSpecs`设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="654cf-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="654cf-118">要求</span><span class="sxs-lookup"><span data-stu-id="654cf-118">Requirements</span></span>  
 <span data-ttu-id="654cf-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="654cf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="654cf-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="654cf-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="654cf-121">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="654cf-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="654cf-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="654cf-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="654cf-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="654cf-123">See also</span></span>

- [<span data-ttu-id="654cf-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="654cf-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="654cf-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="654cf-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
