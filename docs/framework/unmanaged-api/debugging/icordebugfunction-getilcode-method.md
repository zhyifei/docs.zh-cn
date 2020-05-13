---
title: ICorDebugFunction::GetILCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213616"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="d4367-102">ICorDebugFunction::GetILCode 方法</span><span class="sxs-lookup"><span data-stu-id="d4367-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="d4367-103">获取表示与此 ICorDebugFunction 对象关联的 Microsoft 中间语言（MSIL）代码的 ICorDebugCode 实例。</span><span class="sxs-lookup"><span data-stu-id="d4367-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4367-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4367-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4367-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4367-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="d4367-106">弄指向实例的指针 `ICorDebugCode` ，如果该函数未编译为 MSIL，则为 null。</span><span class="sxs-lookup"><span data-stu-id="d4367-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4367-107">备注</span><span class="sxs-lookup"><span data-stu-id="d4367-107">Remarks</span></span>  
 <span data-ttu-id="d4367-108">如果此函数允许使用 "编辑并继续"，则该 `GetILCode` 方法将在公共语言运行时（CLR）中获取与此函数的编辑版本代码相对应的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="d4367-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4367-109">要求</span><span class="sxs-lookup"><span data-stu-id="d4367-109">Requirements</span></span>  
 <span data-ttu-id="d4367-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4367-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4367-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4367-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4367-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4367-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4367-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4367-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
