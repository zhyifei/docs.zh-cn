---
title: IMetaDataImport::EnumInterfaceImpls 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447447"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="388c4-102">IMetaDataImport::EnumInterfaceImpls 方法</span><span class="sxs-lookup"><span data-stu-id="388c4-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="388c4-103">枚举表示接口实现的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="388c4-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="388c4-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="388c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="388c4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="388c4-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="388c4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="388c4-107">[in]表示接口实现的 MethodDef 标记是要枚举的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="388c4-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="388c4-108">[out]用于存储的 MethodDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="388c4-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="388c4-109">[in] `rImpls` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="388c4-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="388c4-110">[out]令牌中返回的实际数目`rImpls`。</span><span class="sxs-lookup"><span data-stu-id="388c4-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="388c4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="388c4-111">Return Value</span></span>  
  
|<span data-ttu-id="388c4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="388c4-112">HRESULT</span></span>|<span data-ttu-id="388c4-113">描述</span><span class="sxs-lookup"><span data-stu-id="388c4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="388c4-114">`EnumInterfaceImpls` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="388c4-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="388c4-115">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="388c4-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="388c4-116">在这种情况下，`pcImpls`设置为零。</span><span class="sxs-lookup"><span data-stu-id="388c4-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="388c4-117">要求</span><span class="sxs-lookup"><span data-stu-id="388c4-117">Requirements</span></span>  
 <span data-ttu-id="388c4-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="388c4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388c4-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="388c4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="388c4-120">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="388c4-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="388c4-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="388c4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388c4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="388c4-122">See Also</span></span>  
 [<span data-ttu-id="388c4-123">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="388c4-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="388c4-124">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="388c4-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
