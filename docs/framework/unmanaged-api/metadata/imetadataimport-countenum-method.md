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
ms.openlocfilehash: 1f657957d42cef1421ab3aa19f297bd04b0cacd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781332"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="12899-102">IMetaDataImport::CountEnum 方法</span><span class="sxs-lookup"><span data-stu-id="12899-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="12899-103">检索由指定枚举器枚举中获取元素的数。</span><span class="sxs-lookup"><span data-stu-id="12899-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12899-104">语法</span><span class="sxs-lookup"><span data-stu-id="12899-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12899-105">参数</span><span class="sxs-lookup"><span data-stu-id="12899-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="12899-106">[in]枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="12899-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="12899-107">[out]枚举的元素数。</span><span class="sxs-lookup"><span data-stu-id="12899-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12899-108">备注</span><span class="sxs-lookup"><span data-stu-id="12899-108">Remarks</span></span>  
 <span data-ttu-id="12899-109">通过指定的句柄`hEnum`获取从以前`Enum`*名称*调用 (例如， [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="12899-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12899-110">要求</span><span class="sxs-lookup"><span data-stu-id="12899-110">Requirements</span></span>  
 <span data-ttu-id="12899-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12899-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12899-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12899-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12899-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="12899-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12899-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12899-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12899-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="12899-115">See also</span></span>

- [<span data-ttu-id="12899-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="12899-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="12899-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="12899-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
