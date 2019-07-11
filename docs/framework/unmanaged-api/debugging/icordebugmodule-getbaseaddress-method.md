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
ms.openlocfilehash: 9ed6344f9a37d246a551699c94046b8c2b473fd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762689"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="bc424-102">ICorDebugModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="bc424-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="bc424-103">获取该模块的基址。</span><span class="sxs-lookup"><span data-stu-id="bc424-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc424-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc424-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc424-105">参数</span><span class="sxs-lookup"><span data-stu-id="bc424-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="bc424-106">[out]一个`CORDB_ADDRESS`，它指定该模块的基址。</span><span class="sxs-lookup"><span data-stu-id="bc424-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc424-107">备注</span><span class="sxs-lookup"><span data-stu-id="bc424-107">Remarks</span></span>  
 <span data-ttu-id="bc424-108">如果该模块是一个本机映像 （即，如果该模块由本机映像生成器 NGen.exe 生成），其基址将为零。</span><span class="sxs-lookup"><span data-stu-id="bc424-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc424-109">要求</span><span class="sxs-lookup"><span data-stu-id="bc424-109">Requirements</span></span>  
 <span data-ttu-id="bc424-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc424-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc424-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc424-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc424-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc424-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc424-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc424-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc424-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc424-114">See also</span></span>
