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
ms.openlocfilehash: d715f5842bb7f75da5311d34bf7d4596f0801a92
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210275"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="50df9-102">ICorDebugILFrame::GetArgument 方法</span><span class="sxs-lookup"><span data-stu-id="50df9-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="50df9-103">获取此 Microsoft 中间语言（MSIL）堆栈帧中的指定参数的值。</span><span class="sxs-lookup"><span data-stu-id="50df9-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50df9-104">语法</span><span class="sxs-lookup"><span data-stu-id="50df9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50df9-105">参数</span><span class="sxs-lookup"><span data-stu-id="50df9-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="50df9-106">中此 MSIL 堆栈帧中的参数的索引。</span><span class="sxs-lookup"><span data-stu-id="50df9-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="50df9-107">[out] 一个指向 ICorDebugValue 对象地址的指针，该对象表示检索到的值。</span><span class="sxs-lookup"><span data-stu-id="50df9-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50df9-108">备注</span><span class="sxs-lookup"><span data-stu-id="50df9-108">Remarks</span></span>  
 <span data-ttu-id="50df9-109">此 `GetArgument` 方法可用于 MSIL 堆栈帧或实时（JIT）编译的帧中。</span><span class="sxs-lookup"><span data-stu-id="50df9-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50df9-110">要求</span><span class="sxs-lookup"><span data-stu-id="50df9-110">Requirements</span></span>  
 <span data-ttu-id="50df9-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50df9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50df9-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50df9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50df9-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50df9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50df9-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50df9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
