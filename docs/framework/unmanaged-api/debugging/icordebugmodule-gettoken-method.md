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
ms.openlocfilehash: 683c2853ea2ed43e61eb666ec56619cb58cde273
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129494"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="e7413-102">ICorDebugModule::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="e7413-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="e7413-103">获取此模块的表项的标记。</span><span class="sxs-lookup"><span data-stu-id="e7413-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7413-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7413-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7413-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7413-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="e7413-106">弄指向引用模块元数据的 `mdModule` 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="e7413-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7413-107">备注</span><span class="sxs-lookup"><span data-stu-id="e7413-107">Remarks</span></span>  
 <span data-ttu-id="e7413-108">该令牌可以传递到[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)、 [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)和[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)元数据导入接口。</span><span class="sxs-lookup"><span data-stu-id="e7413-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7413-109">要求</span><span class="sxs-lookup"><span data-stu-id="e7413-109">Requirements</span></span>  
 <span data-ttu-id="e7413-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7413-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7413-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7413-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7413-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7413-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7413-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7413-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7413-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7413-114">See also</span></span>

- [<span data-ttu-id="e7413-115">元数据</span><span class="sxs-lookup"><span data-stu-id="e7413-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
