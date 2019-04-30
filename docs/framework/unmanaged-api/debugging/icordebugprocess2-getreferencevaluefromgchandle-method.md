---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08bf4022f7cd7f85ffe7939c16fd47950e131a77
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948884"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="199d6-102">ICorDebugProcess2::GetReferenceValueFromGCHandle 方法</span><span class="sxs-lookup"><span data-stu-id="199d6-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="199d6-103">获取指定的托管对象具有垃圾回收句柄引用指向。</span><span class="sxs-lookup"><span data-stu-id="199d6-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="199d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="199d6-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="199d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="199d6-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="199d6-106">[in]指向具有垃圾回收句柄的托管对象的指针。</span><span class="sxs-lookup"><span data-stu-id="199d6-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="199d6-107">此值是<xref:System.IntPtr>对象，并可以从检索<xref:System.Runtime.InteropServices.GCHandle>托管对象。</span><span class="sxs-lookup"><span data-stu-id="199d6-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="199d6-108">[out]指向一个 ICorDebugReferenceValue 对象，表示对指定的托管对象的引用的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="199d6-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="199d6-109">备注</span><span class="sxs-lookup"><span data-stu-id="199d6-109">Remarks</span></span>  
 <span data-ttu-id="199d6-110">不要混淆垃圾回收引用值与返回的引用值。</span><span class="sxs-lookup"><span data-stu-id="199d6-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="199d6-111">返回的引用的行为类似于普通的引用。</span><span class="sxs-lookup"><span data-stu-id="199d6-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="199d6-112">禁用断点后继续执行代码时。</span><span class="sxs-lookup"><span data-stu-id="199d6-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="199d6-113">目标对象的生存期由引用值的生存期不受影响。</span><span class="sxs-lookup"><span data-stu-id="199d6-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="199d6-114">`GetReferenceValueFromGCHandle`方法不会验证该句柄。</span><span class="sxs-lookup"><span data-stu-id="199d6-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="199d6-115">因此，`GetReferenceValueFromGCHandle`方法可能会损坏调试器和正在调试如果传递无效的句柄的代码。</span><span class="sxs-lookup"><span data-stu-id="199d6-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="199d6-116">要求</span><span class="sxs-lookup"><span data-stu-id="199d6-116">Requirements</span></span>  
 <span data-ttu-id="199d6-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="199d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="199d6-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="199d6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="199d6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="199d6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="199d6-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="199d6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
