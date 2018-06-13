---
title: IMetaDataImport::GetClassLayout 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b031fc35a4687a8535e3cb5e9ef2a53bab9fe376
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445502"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="4ea8d-102">IMetaDataImport::GetClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="4ea8d-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="4ea8d-103">获取指定的 TypeDef 标记所引用类的布局信息。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ea8d-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ea8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4ea8d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4ea8d-106">[in]具有要返回的布局的类 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="4ea8d-107">[out]值 1、 2、 4、 8 或 16，表示类的包大小之一。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="4ea8d-108">[out]数组[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)值。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4ea8d-109">[in] `rFieldOffset` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="4ea8d-110">[out]在中返回的元素的数目`rFieldOffset`。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="4ea8d-111">[out]以字节为单位的所表示的类的大小`td`。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ea8d-112">要求</span><span class="sxs-lookup"><span data-stu-id="4ea8d-112">Requirements</span></span>  
 <span data-ttu-id="4ea8d-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea8d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ea8d-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ea8d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ea8d-115">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4ea8d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ea8d-116">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea8d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea8d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ea8d-117">See Also</span></span>  
 [<span data-ttu-id="4ea8d-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4ea8d-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4ea8d-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4ea8d-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
