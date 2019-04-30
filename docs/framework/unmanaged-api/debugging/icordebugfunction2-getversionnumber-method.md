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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc9c2af62184c83857b82445941f6087a05c2c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995600"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="fb2dc-102">ICorDebugFunction2::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="fb2dc-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="fb2dc-103">获取此函数的编辑并继续版本。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb2dc-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb2dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb2dc-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="fb2dc-106">[out]指向一个整数，表示由此 ICorDebugFunction2 对象的函数的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb2dc-107">备注</span><span class="sxs-lookup"><span data-stu-id="fb2dc-107">Remarks</span></span>  
 <span data-ttu-id="fb2dc-108">跟踪在调试会话期间为每个模块所进行的编辑次数的运行时。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="fb2dc-109">一个函数的版本编号是一个超过数目的引入了函数的编辑。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="fb2dc-110">函数的原始版本是版本 1。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-110">The function's original version is version 1.</span></span> <span data-ttu-id="fb2dc-111">该数字递增模块每次都[ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)调用该模块。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="fb2dc-112">因此，如果函数的主体已对的第一个和第三个调用中替换`ICorDebugModule2::ApplyChanges`，`GetVersionNumber`可能会返回版本 1、 2 或 4 表示该函数，但没有版本 3。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="fb2dc-113">（该函数会有任何版本 3。）</span><span class="sxs-lookup"><span data-stu-id="fb2dc-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="fb2dc-114">对于每个模块中分别跟踪的版本号。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="fb2dc-115">因此，如果你在第 1 单元，并对模块 2 未执行四个编辑，第 1 单元在下一次编辑将到第 1 单元中的所有已编辑函数分配版本号为 6。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="fb2dc-116">如果编辑收尾工作了模块 2 相同，第 2 单元中的函数将获得 2 的版本号。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="fb2dc-117">通过获取版本号`GetVersionNumber`方法可能会低于通过获取[icordebugfunction:: Getcurrentversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="fb2dc-118">[Icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)方法执行相同的操作`ICorDebugFunction2::GetVersionNumber`。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb2dc-119">要求</span><span class="sxs-lookup"><span data-stu-id="fb2dc-119">Requirements</span></span>  
 <span data-ttu-id="fb2dc-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb2dc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb2dc-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb2dc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb2dc-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb2dc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb2dc-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb2dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
