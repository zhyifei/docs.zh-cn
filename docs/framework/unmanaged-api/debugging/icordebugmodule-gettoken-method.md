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
ms.openlocfilehash: a6aff37a480460bfed7064d59b4c5276daf3207c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212495"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="cfd64-102">ICorDebugModule::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="cfd64-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="cfd64-103">获取此模块的表项的标记。</span><span class="sxs-lookup"><span data-stu-id="cfd64-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd64-104">语法</span><span class="sxs-lookup"><span data-stu-id="cfd64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfd64-105">参数</span><span class="sxs-lookup"><span data-stu-id="cfd64-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="cfd64-106">弄指向 `mdModule` 引用模块元数据的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="cfd64-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfd64-107">备注</span><span class="sxs-lookup"><span data-stu-id="cfd64-107">Remarks</span></span>  
 <span data-ttu-id="cfd64-108">该令牌可以传递到[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)、 [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)和[IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md)元数据导入接口。</span><span class="sxs-lookup"><span data-stu-id="cfd64-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd64-109">要求</span><span class="sxs-lookup"><span data-stu-id="cfd64-109">Requirements</span></span>  
 <span data-ttu-id="cfd64-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd64-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfd64-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfd64-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfd64-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfd64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfd64-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfd64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd64-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfd64-114">See also</span></span>

- [<span data-ttu-id="cfd64-115">元数据</span><span class="sxs-lookup"><span data-stu-id="cfd64-115">Metadata</span></span>](../metadata/index.md)
