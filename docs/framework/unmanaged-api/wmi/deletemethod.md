---
title: 删除方法函数（非托管 API 引用）
description: DeleteMethod 函数从 CIM 类定义中删除指定的方法。
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4059555d74c0b0f151332ddcf9faedecf238e795
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174987"
---
# <a name="deletemethod-function"></a><span data-ttu-id="64636-103">DeleteMethod 函数</span><span class="sxs-lookup"><span data-stu-id="64636-103">DeleteMethod function</span></span>
<span data-ttu-id="64636-104">从 CIM 类定义中删除指定的方法。</span><span class="sxs-lookup"><span data-stu-id="64636-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="64636-105">语法</span><span class="sxs-lookup"><span data-stu-id="64636-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="64636-106">parameters</span><span class="sxs-lookup"><span data-stu-id="64636-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="64636-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="64636-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="64636-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="64636-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="64636-109">[在]要从类表中删除的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="64636-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="64636-110">`wszName`必须是指向有效`LPCWSTR`指针的 指针。</span><span class="sxs-lookup"><span data-stu-id="64636-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="64636-111">返回值</span><span class="sxs-lookup"><span data-stu-id="64636-111">Return value</span></span>

<span data-ttu-id="64636-112">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="64636-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="64636-113">一直</span><span class="sxs-lookup"><span data-stu-id="64636-113">Constant</span></span>  |<span data-ttu-id="64636-114">值</span><span class="sxs-lookup"><span data-stu-id="64636-114">Value</span></span>  |<span data-ttu-id="64636-115">说明</span><span class="sxs-lookup"><span data-stu-id="64636-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="64636-116">0 x80041002</span><span class="sxs-lookup"><span data-stu-id="64636-116">0x80041002</span></span> | <span data-ttu-id="64636-117">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="64636-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="64636-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="64636-118">0x80041006</span></span> | <span data-ttu-id="64636-119">内存不足，无法完成此操作。</span><span class="sxs-lookup"><span data-stu-id="64636-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="64636-120">0</span><span class="sxs-lookup"><span data-stu-id="64636-120">0</span></span> | <span data-ttu-id="64636-121">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="64636-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="64636-122">备注</span><span class="sxs-lookup"><span data-stu-id="64636-122">Remarks</span></span>

<span data-ttu-id="64636-123">此函数包装对[IWbemClassObject：:Delete 方法的](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod)调用。</span><span class="sxs-lookup"><span data-stu-id="64636-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="64636-124">对于指向 CIM 实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针，不支持方法删除。</span><span class="sxs-lookup"><span data-stu-id="64636-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="64636-125">要求</span><span class="sxs-lookup"><span data-stu-id="64636-125">Requirements</span></span>  
 <span data-ttu-id="64636-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64636-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64636-127">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="64636-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="64636-128">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64636-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64636-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64636-129">See also</span></span>

- [<span data-ttu-id="64636-130">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="64636-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
