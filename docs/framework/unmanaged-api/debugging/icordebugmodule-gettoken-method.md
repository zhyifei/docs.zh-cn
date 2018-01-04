---
title: "ICorDebugModule::GetToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 651612b07a69f0cbcc9c818fe7627bf496f6d68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="799a9-102">ICorDebugModule::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="799a9-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="799a9-103">获取此模块的表项的令牌。</span><span class="sxs-lookup"><span data-stu-id="799a9-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="799a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="799a9-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="799a9-105">参数</span><span class="sxs-lookup"><span data-stu-id="799a9-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="799a9-106">[out]指向的指针`mdModule`引用模块的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="799a9-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="799a9-107">备注</span><span class="sxs-lookup"><span data-stu-id="799a9-107">Remarks</span></span>  
 <span data-ttu-id="799a9-108">标记可以传递到[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)， [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)，和[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)元数据导入接口。</span><span class="sxs-lookup"><span data-stu-id="799a9-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="799a9-109">惠?</span><span class="sxs-lookup"><span data-stu-id="799a9-109">Requirements</span></span>  
 <span data-ttu-id="799a9-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="799a9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="799a9-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="799a9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="799a9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="799a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="799a9-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="799a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799a9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="799a9-114">See Also</span></span>  
 [<span data-ttu-id="799a9-115">元数据</span><span class="sxs-lookup"><span data-stu-id="799a9-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
