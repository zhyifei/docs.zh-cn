---
title: ICorDebugModule::GetBaseAddress 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 763f2872099fac87138b7e1ab058c60475892b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107414"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="7f442-102">ICorDebugModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="7f442-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="7f442-103">获取该模块的基址。</span><span class="sxs-lookup"><span data-stu-id="7f442-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f442-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f442-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f442-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f442-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="7f442-106">[out]一个`CORDB_ADDRESS`，它指定该模块的基址。</span><span class="sxs-lookup"><span data-stu-id="7f442-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f442-107">备注</span><span class="sxs-lookup"><span data-stu-id="7f442-107">Remarks</span></span>  
 <span data-ttu-id="7f442-108">如果该模块是一个本机映像 （即，如果该模块由本机映像生成器 NGen.exe 生成），其基址将为零。</span><span class="sxs-lookup"><span data-stu-id="7f442-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f442-109">要求</span><span class="sxs-lookup"><span data-stu-id="7f442-109">Requirements</span></span>  
 <span data-ttu-id="7f442-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f442-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f442-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f442-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f442-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f442-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7f442-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7f442-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f442-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f442-114">See also</span></span>
