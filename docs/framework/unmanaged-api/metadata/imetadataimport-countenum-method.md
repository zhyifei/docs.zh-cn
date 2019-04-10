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
ms.openlocfilehash: b5015dc42497d269cdc2de944f14454558be6c07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142982"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="d890b-102">IMetaDataImport::CountEnum 方法</span><span class="sxs-lookup"><span data-stu-id="d890b-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="d890b-103">检索由指定枚举器枚举中获取元素的数。</span><span class="sxs-lookup"><span data-stu-id="d890b-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d890b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d890b-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d890b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d890b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d890b-106">[in]枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="d890b-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="d890b-107">[out]枚举的元素数。</span><span class="sxs-lookup"><span data-stu-id="d890b-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d890b-108">备注</span><span class="sxs-lookup"><span data-stu-id="d890b-108">Remarks</span></span>  
 <span data-ttu-id="d890b-109">通过指定的句柄`hEnum`获取从以前`Enum`*名称*调用 (例如， [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="d890b-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d890b-110">要求</span><span class="sxs-lookup"><span data-stu-id="d890b-110">Requirements</span></span>  
 <span data-ttu-id="d890b-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d890b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d890b-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d890b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d890b-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d890b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d890b-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d890b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d890b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d890b-115">See also</span></span>

- [<span data-ttu-id="d890b-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d890b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d890b-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d890b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
