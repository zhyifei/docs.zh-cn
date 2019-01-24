---
title: IMetaDataImport::CountEnum 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b48ff81fad397adcd5b2d0caae961484bfea5e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706386"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="3435e-102">IMetaDataImport::CountEnum 方法</span><span class="sxs-lookup"><span data-stu-id="3435e-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="3435e-103">检索由指定枚举器枚举中获取元素的数。</span><span class="sxs-lookup"><span data-stu-id="3435e-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3435e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3435e-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3435e-105">参数</span><span class="sxs-lookup"><span data-stu-id="3435e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="3435e-106">[in]枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="3435e-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="3435e-107">[out]枚举的元素数。</span><span class="sxs-lookup"><span data-stu-id="3435e-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3435e-108">备注</span><span class="sxs-lookup"><span data-stu-id="3435e-108">Remarks</span></span>  
 <span data-ttu-id="3435e-109">通过指定的句柄`hEnum`获取从以前`Enum`*名称*调用 (例如， [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="3435e-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3435e-110">要求</span><span class="sxs-lookup"><span data-stu-id="3435e-110">Requirements</span></span>  
 <span data-ttu-id="3435e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3435e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3435e-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3435e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3435e-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3435e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3435e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3435e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3435e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3435e-115">See also</span></span>
- [<span data-ttu-id="3435e-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3435e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3435e-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3435e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
