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
ms.openlocfilehash: 1653913ca7410728f0f90a546f613a9d8b88be7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414048"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="b648f-102">ICorDebugILFrame::GetArgument 方法</span><span class="sxs-lookup"><span data-stu-id="b648f-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="b648f-103">此 Microsoft 中间语言 (MSIL) 堆栈帧中获取指定的自变量的值。</span><span class="sxs-lookup"><span data-stu-id="b648f-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b648f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b648f-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b648f-105">参数</span><span class="sxs-lookup"><span data-stu-id="b648f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="b648f-106">[in]此 MSIL 堆栈帧中的自变量的索引。</span><span class="sxs-lookup"><span data-stu-id="b648f-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b648f-107">[out]指向一个 ICorDebugValue 对象，表示检索到的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b648f-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b648f-108">备注</span><span class="sxs-lookup"><span data-stu-id="b648f-108">Remarks</span></span>  
 <span data-ttu-id="b648f-109">`GetArgument` MSIL 堆栈帧中或实时 (JIT) 编译框架中，可以使用方法。</span><span class="sxs-lookup"><span data-stu-id="b648f-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b648f-110">要求</span><span class="sxs-lookup"><span data-stu-id="b648f-110">Requirements</span></span>  
 <span data-ttu-id="b648f-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b648f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b648f-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b648f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b648f-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b648f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b648f-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b648f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
