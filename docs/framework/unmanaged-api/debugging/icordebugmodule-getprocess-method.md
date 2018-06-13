---
title: ICorDebugModule::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: add7239feb1cf6dab0fabe12e178336921211190
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414201"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="09bfd-102">ICorDebugModule::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="09bfd-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="09bfd-103">获取此模块包含进程。</span><span class="sxs-lookup"><span data-stu-id="09bfd-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09bfd-104">语法</span><span class="sxs-lookup"><span data-stu-id="09bfd-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09bfd-105">参数</span><span class="sxs-lookup"><span data-stu-id="09bfd-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="09bfd-106">[out]指向一个 ICorDebugProcess 对象，表示包含此模块的过程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="09bfd-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09bfd-107">要求</span><span class="sxs-lookup"><span data-stu-id="09bfd-107">Requirements</span></span>  
 <span data-ttu-id="09bfd-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09bfd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09bfd-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09bfd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09bfd-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09bfd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09bfd-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09bfd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
