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
ms.openlocfilehash: c10c45c4450e02d633ebeeca15da95b7c95ff0b4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212524"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="f2553-102">ICorDebugModule::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="f2553-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="f2553-103">获取此模块的包含进程。</span><span class="sxs-lookup"><span data-stu-id="f2553-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2553-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2553-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2553-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2553-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="f2553-106">弄指向 ICorDebugProcess 对象的地址的指针，该对象表示包含此模块的进程。</span><span class="sxs-lookup"><span data-stu-id="f2553-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2553-107">要求</span><span class="sxs-lookup"><span data-stu-id="f2553-107">Requirements</span></span>  
 <span data-ttu-id="f2553-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2553-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2553-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2553-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2553-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2553-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2553-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2553-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
