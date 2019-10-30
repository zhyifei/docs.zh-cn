---
title: ICorDebugFrame::GetCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: 9a4f533c0ab817d800c2d35b7d64c7aee78faaea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121169"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="82f11-102">ICorDebugFrame::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="82f11-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="82f11-103">获取一个指针，该指针指向与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="82f11-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f11-104">语法</span><span class="sxs-lookup"><span data-stu-id="82f11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82f11-105">参数</span><span class="sxs-lookup"><span data-stu-id="82f11-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="82f11-106">弄指向 ICorDebugCode 对象的地址的指针，该对象表示与此帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="82f11-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f11-107">要求</span><span class="sxs-lookup"><span data-stu-id="82f11-107">Requirements</span></span>  
 <span data-ttu-id="82f11-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82f11-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f11-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82f11-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82f11-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82f11-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82f11-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f11-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
