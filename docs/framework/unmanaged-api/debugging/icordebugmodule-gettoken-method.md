---
title: ICorDebugModule::GetToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c28182feff8e4b7d49b7d068da1496d44fa2f917
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150353"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="6fc56-102">ICorDebugModule::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="6fc56-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="6fc56-103">获取此模块的表项的标记。</span><span class="sxs-lookup"><span data-stu-id="6fc56-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc56-104">语法</span><span class="sxs-lookup"><span data-stu-id="6fc56-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fc56-105">参数</span><span class="sxs-lookup"><span data-stu-id="6fc56-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="6fc56-106">[out]一个指向`mdModule`引用模块的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="6fc56-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fc56-107">备注</span><span class="sxs-lookup"><span data-stu-id="6fc56-107">Remarks</span></span>  
 <span data-ttu-id="6fc56-108">可以将令牌传递给[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)， [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)，并[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)元数据导入接口。</span><span class="sxs-lookup"><span data-stu-id="6fc56-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fc56-109">要求</span><span class="sxs-lookup"><span data-stu-id="6fc56-109">Requirements</span></span>  
 <span data-ttu-id="6fc56-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc56-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fc56-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fc56-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fc56-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fc56-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6fc56-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6fc56-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6fc56-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fc56-114">See also</span></span>

- [<span data-ttu-id="6fc56-115">元数据</span><span class="sxs-lookup"><span data-stu-id="6fc56-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
