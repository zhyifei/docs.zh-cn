---
title: "IMetaDataImport::CloseEnum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.CloseEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 80e156cd92519fc78f2a3076d03b279b7a63c1d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="73562-102">IMetaDataImport::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="73562-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="73562-103">关闭的枚举器由指定的句柄。</span><span class="sxs-lookup"><span data-stu-id="73562-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73562-104">语法</span><span class="sxs-lookup"><span data-stu-id="73562-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73562-105">参数</span><span class="sxs-lookup"><span data-stu-id="73562-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="73562-106">[in]枚举器，以关闭句柄。</span><span class="sxs-lookup"><span data-stu-id="73562-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73562-107">备注</span><span class="sxs-lookup"><span data-stu-id="73562-107">Remarks</span></span>  
 <span data-ttu-id="73562-108">指定的句柄`hEnum`从以前获取`Enum`*名称*调用 (例如， [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="73562-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73562-109">要求</span><span class="sxs-lookup"><span data-stu-id="73562-109">Requirements</span></span>  
 <span data-ttu-id="73562-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73562-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73562-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73562-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73562-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="73562-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73562-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73562-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73562-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73562-114">See Also</span></span>  
 [<span data-ttu-id="73562-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="73562-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="73562-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="73562-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
