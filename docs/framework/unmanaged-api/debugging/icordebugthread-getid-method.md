---
title: "ICorDebugThread::GetID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31ae48d62221d45a8457c304a1929886738190c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="6fed4-102">ICorDebugThread::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="6fed4-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="6fed4-103">获取此 ICorDebugThread 的活动部分的当前操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="6fed4-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fed4-104">语法</span><span class="sxs-lookup"><span data-stu-id="6fed4-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fed4-105">参数</span><span class="sxs-lookup"><span data-stu-id="6fed4-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="6fed4-106">[out]线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="6fed4-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fed4-107">备注</span><span class="sxs-lookup"><span data-stu-id="6fed4-107">Remarks</span></span>  
 <span data-ttu-id="6fed4-108">操作系统标识符可能发生更改的过程中，执行过程，并且可以的线程的不同部分的值。</span><span class="sxs-lookup"><span data-stu-id="6fed4-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fed4-109">要求</span><span class="sxs-lookup"><span data-stu-id="6fed4-109">Requirements</span></span>  
 <span data-ttu-id="6fed4-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fed4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fed4-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fed4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fed4-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fed4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fed4-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fed4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
