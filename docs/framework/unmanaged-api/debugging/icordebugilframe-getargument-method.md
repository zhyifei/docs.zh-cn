---
title: ICorDebugILFrame::GetArgument 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e9f627f1ba213f663f042d1107afd1eb05b56b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757862"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="67c81-102">ICorDebugILFrame::GetArgument 方法</span><span class="sxs-lookup"><span data-stu-id="67c81-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="67c81-103">获取此 Microsoft 中间语言 (MSIL) 堆栈帧中的指定参数的值。</span><span class="sxs-lookup"><span data-stu-id="67c81-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c81-104">语法</span><span class="sxs-lookup"><span data-stu-id="67c81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67c81-105">参数</span><span class="sxs-lookup"><span data-stu-id="67c81-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="67c81-106">[in]在此 MSIL 堆栈帧中的参数的索引。</span><span class="sxs-lookup"><span data-stu-id="67c81-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="67c81-107">[out]指向表示检索到的值的 ICorDebugValue 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="67c81-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c81-108">备注</span><span class="sxs-lookup"><span data-stu-id="67c81-108">Remarks</span></span>  
 <span data-ttu-id="67c81-109">`GetArgument` MSIL 堆栈帧中或在实时 (JIT) 编译帧中，可以使用方法。</span><span class="sxs-lookup"><span data-stu-id="67c81-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c81-110">要求</span><span class="sxs-lookup"><span data-stu-id="67c81-110">Requirements</span></span>  
 <span data-ttu-id="67c81-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67c81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c81-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67c81-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67c81-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67c81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67c81-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
