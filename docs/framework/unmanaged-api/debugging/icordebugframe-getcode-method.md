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
ms.openlocfilehash: c8914ba1090ec5fd6540e9ead302675cb44f37e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208598"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="8b260-102">ICorDebugFrame::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="8b260-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="8b260-103">获取一个指针，该指针指向与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="8b260-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b260-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b260-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b260-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b260-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="8b260-106">弄指向 ICorDebugCode 对象的地址的指针，该对象表示与此帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="8b260-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b260-107">要求</span><span class="sxs-lookup"><span data-stu-id="8b260-107">Requirements</span></span>  
 <span data-ttu-id="8b260-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b260-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b260-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b260-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b260-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b260-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b260-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b260-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
