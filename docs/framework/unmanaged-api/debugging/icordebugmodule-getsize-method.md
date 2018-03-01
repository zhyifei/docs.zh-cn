---
title: "ICorDebugModule::GetSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9474b48526e2ba6292c28e5e66eb97f8e57f2a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="e5f8b-102">ICorDebugModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="e5f8b-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="e5f8b-103">获取用字节表示，该模块的大小。</span><span class="sxs-lookup"><span data-stu-id="e5f8b-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5f8b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5f8b-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5f8b-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="e5f8b-106">[out]以字节为单位的模块的大小。</span><span class="sxs-lookup"><span data-stu-id="e5f8b-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="e5f8b-107">如果该模块通过本机映像生成器 (NGen.exe) 生成的该模块的大小将为零。</span><span class="sxs-lookup"><span data-stu-id="e5f8b-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f8b-108">惠?</span><span class="sxs-lookup"><span data-stu-id="e5f8b-108">Requirements</span></span>  
 <span data-ttu-id="e5f8b-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5f8b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f8b-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5f8b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5f8b-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5f8b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5f8b-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f8b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
