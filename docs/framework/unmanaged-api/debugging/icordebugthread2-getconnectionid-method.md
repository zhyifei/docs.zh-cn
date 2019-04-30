---
title: ICorDebugThread2::GetConnectionID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d51e21eab4ac1edc81b58171e5382ada170a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946325"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="288a1-102">ICorDebugThread2::GetConnectionID 方法</span><span class="sxs-lookup"><span data-stu-id="288a1-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="288a1-103">获取此 ICorDebugThread2 对象的连接标识符。</span><span class="sxs-lookup"><span data-stu-id="288a1-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="288a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="288a1-104">Syntax</span></span>  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="288a1-105">参数</span><span class="sxs-lookup"><span data-stu-id="288a1-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="288a1-106">[out]一个`CONNID`表示的连接标识符。</span><span class="sxs-lookup"><span data-stu-id="288a1-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="288a1-107">备注</span><span class="sxs-lookup"><span data-stu-id="288a1-107">Remarks</span></span>  
 <span data-ttu-id="288a1-108">`GetConnectionID`方法将返回 0 中的`pdwConnectionId`参数，如果此线程不是连接的一部分。</span><span class="sxs-lookup"><span data-stu-id="288a1-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="288a1-109">如果此线程连接到实例的 Microsoft SQL Server 2005 Analysis Services (SSAS)，`CONNID`映射到服务器进程标识符 (SPID)。</span><span class="sxs-lookup"><span data-stu-id="288a1-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="288a1-110">要求</span><span class="sxs-lookup"><span data-stu-id="288a1-110">Requirements</span></span>  
 <span data-ttu-id="288a1-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="288a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="288a1-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="288a1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="288a1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="288a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="288a1-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="288a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
