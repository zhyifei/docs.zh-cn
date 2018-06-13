---
title: IMetaDataImport::CloseEnum 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d81f9b0107fd927ddfda24cfd0ea3249e4c8651
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448812"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="15f76-102">IMetaDataImport::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="15f76-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="15f76-103">关闭的枚举器由指定的句柄。</span><span class="sxs-lookup"><span data-stu-id="15f76-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f76-104">语法</span><span class="sxs-lookup"><span data-stu-id="15f76-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15f76-105">参数</span><span class="sxs-lookup"><span data-stu-id="15f76-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="15f76-106">[in]枚举器，以关闭句柄。</span><span class="sxs-lookup"><span data-stu-id="15f76-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f76-107">备注</span><span class="sxs-lookup"><span data-stu-id="15f76-107">Remarks</span></span>  
 <span data-ttu-id="15f76-108">指定的句柄`hEnum`从以前获取`Enum`*名称*调用 (例如， [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="15f76-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f76-109">要求</span><span class="sxs-lookup"><span data-stu-id="15f76-109">Requirements</span></span>  
 <span data-ttu-id="15f76-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15f76-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f76-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15f76-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15f76-112">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="15f76-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15f76-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f76-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f76-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="15f76-114">See Also</span></span>  
 [<span data-ttu-id="15f76-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="15f76-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="15f76-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="15f76-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
