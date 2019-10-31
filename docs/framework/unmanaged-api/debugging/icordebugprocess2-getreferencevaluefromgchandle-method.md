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
ms.openlocfilehash: 47647bf0460507b4c88b47bf87bfcc3bf620aecc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137211"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="3d9f9-102">ICorDebugProcess2::GetReferenceValueFromGCHandle 方法</span><span class="sxs-lookup"><span data-stu-id="3d9f9-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="3d9f9-103">获取指向具有垃圾回收句柄的指定托管对象的引用指针。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d9f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d9f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="3d9f9-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="3d9f9-106">中指向具有垃圾回收句柄的托管对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="3d9f9-107">此值是 <xref:System.IntPtr> 对象，可以从托管对象的 <xref:System.Runtime.InteropServices.GCHandle> 中检索。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="3d9f9-108">弄指向 ICorDebugReferenceValue 对象的地址的指针，该对象表示对指定托管对象的引用。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d9f9-109">备注</span><span class="sxs-lookup"><span data-stu-id="3d9f9-109">Remarks</span></span>  
 <span data-ttu-id="3d9f9-110">不要将返回的引用值与垃圾回收引用值混淆。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="3d9f9-111">返回的引用的行为与常规引用相同。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="3d9f9-112">当代码在断点后面继续执行时，它会被禁用。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="3d9f9-113">目标对象的生存期不受引用值的生存期的影响。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d9f9-114">`GetReferenceValueFromGCHandle` 方法不会验证句柄。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="3d9f9-115">因此，如果传递了无效的句柄，`GetReferenceValueFromGCHandle` 方法可能会损坏调试器和正在调试的代码。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9f9-116">要求</span><span class="sxs-lookup"><span data-stu-id="3d9f9-116">Requirements</span></span>  
 <span data-ttu-id="3d9f9-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3d9f9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9f9-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d9f9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d9f9-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9f9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d9f9-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9f9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
