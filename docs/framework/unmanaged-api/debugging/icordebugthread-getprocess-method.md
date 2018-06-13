---
title: ICorDebugThread::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b41c7eeccad8b3f685c81e6afc23eaf19d862182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417607"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="980dd-102">ICorDebugThread::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="980dd-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="980dd-103">获取此 ICorDebugThread 构成一部分的进程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="980dd-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="980dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="980dd-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="980dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="980dd-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="980dd-106">[out]ICorDebugProcess 接口对象表示进程的地址指针。</span><span class="sxs-lookup"><span data-stu-id="980dd-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="980dd-107">要求</span><span class="sxs-lookup"><span data-stu-id="980dd-107">Requirements</span></span>  
 <span data-ttu-id="980dd-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="980dd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="980dd-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="980dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="980dd-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="980dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="980dd-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="980dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
