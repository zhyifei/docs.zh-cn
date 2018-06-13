---
title: ICorDebugModule::GetSize 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d741bda5426dee1292df0e6fd9107cc2f44c8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413314"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="b10ef-102">ICorDebugModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="b10ef-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="b10ef-103">获取用字节表示，该模块的大小。</span><span class="sxs-lookup"><span data-stu-id="b10ef-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b10ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="b10ef-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b10ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="b10ef-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="b10ef-106">[out]以字节为单位的模块的大小。</span><span class="sxs-lookup"><span data-stu-id="b10ef-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="b10ef-107">如果该模块通过本机映像生成器 (NGen.exe) 生成的该模块的大小将为零。</span><span class="sxs-lookup"><span data-stu-id="b10ef-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b10ef-108">要求</span><span class="sxs-lookup"><span data-stu-id="b10ef-108">Requirements</span></span>  
 <span data-ttu-id="b10ef-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b10ef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b10ef-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b10ef-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b10ef-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b10ef-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b10ef-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b10ef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
