---
title: ICorDebugFrame::GetCaller 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: b29de0b70daa783197e78fe985d379d4124bc140
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205151"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="b26e1-102">ICorDebugFrame::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="b26e1-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="b26e1-103">获取一个指针，该指针指向当前链中调用此帧的 ICorDebugFrame 对象。</span><span class="sxs-lookup"><span data-stu-id="b26e1-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b26e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="b26e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b26e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="b26e1-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="b26e1-106">弄指向 `ICorDebugFrame` 表示调用帧的对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b26e1-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="b26e1-107">如果被调用的帧是当前链中最外层的帧，则此值为 null。</span><span class="sxs-lookup"><span data-stu-id="b26e1-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b26e1-108">要求</span><span class="sxs-lookup"><span data-stu-id="b26e1-108">Requirements</span></span>  
 <span data-ttu-id="b26e1-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b26e1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b26e1-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b26e1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b26e1-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b26e1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b26e1-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b26e1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
