---
title: ICorDebugProcess6::GetExportStepInfo 方法
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 9d195c61d95f084c7b6b40d2c81623fd81cd94cf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206360"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="09113-102">ICorDebugProcess6::GetExportStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="09113-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="09113-103">提供运行时导出功能信息以帮助单步调试托管代码。</span><span class="sxs-lookup"><span data-stu-id="09113-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09113-104">语法</span><span class="sxs-lookup"><span data-stu-id="09113-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09113-105">参数</span><span class="sxs-lookup"><span data-stu-id="09113-105">Parameters</span></span>  
 <span data-ttu-id="09113-106">psz导出名</span><span class="sxs-lookup"><span data-stu-id="09113-106">pszExportName</span></span>  
 <span data-ttu-id="09113-107">[输入] 如 PE 导出表中所写的运行时间导出函数名。</span><span class="sxs-lookup"><span data-stu-id="09113-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="09113-108">调用类型</span><span class="sxs-lookup"><span data-stu-id="09113-108">invokeKind</span></span>  
 <span data-ttu-id="09113-109">弄一个指针，指向[CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)枚举的成员，该枚举描述导出函数将如何调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="09113-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="09113-110">调用目的</span><span class="sxs-lookup"><span data-stu-id="09113-110">invokePurpose</span></span>  
 <span data-ttu-id="09113-111">弄指向[CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)枚举的成员的指针，该成员描述导出函数将调用托管代码的原因。</span><span class="sxs-lookup"><span data-stu-id="09113-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09113-112">返回值</span><span class="sxs-lookup"><span data-stu-id="09113-112">Return Value</span></span>  
 <span data-ttu-id="09113-113">该方法可以返回下表所列的值。</span><span class="sxs-lookup"><span data-stu-id="09113-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="09113-114">返回值</span><span class="sxs-lookup"><span data-stu-id="09113-114">Return value</span></span>|<span data-ttu-id="09113-115">描述</span><span class="sxs-lookup"><span data-stu-id="09113-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="09113-116">方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="09113-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="09113-117">`pInvokeKind`或 `pInvokePurpose` 为**null**。</span><span class="sxs-lookup"><span data-stu-id="09113-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="09113-118">其他失败 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="09113-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="09113-119">根据需要。</span><span class="sxs-lookup"><span data-stu-id="09113-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09113-120">备注</span><span class="sxs-lookup"><span data-stu-id="09113-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09113-121">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="09113-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09113-122">要求</span><span class="sxs-lookup"><span data-stu-id="09113-122">Requirements</span></span>  
 <span data-ttu-id="09113-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09113-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09113-124">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09113-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09113-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09113-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09113-126">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09113-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09113-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="09113-127">See also</span></span>

- [<span data-ttu-id="09113-128">“ICor调试进程6”接口</span><span class="sxs-lookup"><span data-stu-id="09113-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="09113-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="09113-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
