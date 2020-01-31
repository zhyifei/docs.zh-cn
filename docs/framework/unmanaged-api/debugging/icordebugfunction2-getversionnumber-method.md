---
title: ICorDebugFunction2::GetVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: d85885d750f3c98e46b3e44418564da18850d3ec
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794488"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="97dbf-102">ICorDebugFunction2::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="97dbf-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="97dbf-103">获取此函数的 "编辑并继续" 版本。</span><span class="sxs-lookup"><span data-stu-id="97dbf-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97dbf-104">语法</span><span class="sxs-lookup"><span data-stu-id="97dbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97dbf-105">参数</span><span class="sxs-lookup"><span data-stu-id="97dbf-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="97dbf-106">弄指向一个整数的指针，该整数是此 ICorDebugFunction2 对象所表示的函数的版本号。</span><span class="sxs-lookup"><span data-stu-id="97dbf-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97dbf-107">备注</span><span class="sxs-lookup"><span data-stu-id="97dbf-107">Remarks</span></span>  
 <span data-ttu-id="97dbf-108">运行时跟踪在调试会话期间对每个模块进行的编辑的次数。</span><span class="sxs-lookup"><span data-stu-id="97dbf-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="97dbf-109">函数的版本号比引入函数的编辑次数多一个。</span><span class="sxs-lookup"><span data-stu-id="97dbf-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="97dbf-110">函数的原始版本是版本1。</span><span class="sxs-lookup"><span data-stu-id="97dbf-110">The function's original version is version 1.</span></span> <span data-ttu-id="97dbf-111">每次调用该模块上的[ICorDebugModule2：： ApplyChanges](icordebugmodule2-applychanges-method.md)时，模块的数字都会递增。</span><span class="sxs-lookup"><span data-stu-id="97dbf-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="97dbf-112">因此，如果在第一次调用和第三次 `ICorDebugModule2::ApplyChanges`调用时已替换函数体，则 `GetVersionNumber` 可能返回该函数的版本1、2或4，但不返回版本3。</span><span class="sxs-lookup"><span data-stu-id="97dbf-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="97dbf-113">（该函数不会有版本3。）</span><span class="sxs-lookup"><span data-stu-id="97dbf-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="97dbf-114">为每个模块单独跟踪版本号。</span><span class="sxs-lookup"><span data-stu-id="97dbf-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="97dbf-115">因此，如果在模块1上执行四个编辑，而在模块2上执行 "无"，则下一次编辑时，模块1将为模块1中的所有编辑函数分配6号。</span><span class="sxs-lookup"><span data-stu-id="97dbf-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="97dbf-116">如果相同的编辑触及模块2，则模块2中的函数将获得版本号2。</span><span class="sxs-lookup"><span data-stu-id="97dbf-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="97dbf-117">`GetVersionNumber` 方法获取的版本号可能低于[ICorDebugFunction：： GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md)获取的版本号。</span><span class="sxs-lookup"><span data-stu-id="97dbf-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="97dbf-118">[ICorDebugCode：： GetVersionNumber](icordebugcode-getversionnumber-method.md)方法执行与 `ICorDebugFunction2::GetVersionNumber`相同的操作。</span><span class="sxs-lookup"><span data-stu-id="97dbf-118">The [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97dbf-119">需求</span><span class="sxs-lookup"><span data-stu-id="97dbf-119">Requirements</span></span>  
 <span data-ttu-id="97dbf-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97dbf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97dbf-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97dbf-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97dbf-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97dbf-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97dbf-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97dbf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
