---
title: QualifierSet_Delete 函数（非托管 API 参考）
description: QualifierSet_Delete 函数按名称删除限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bc26a16650a5beecc17898e0421e79536713deb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798334"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="1e2c2-103">QualifierSet_Delete 函数</span><span class="sxs-lookup"><span data-stu-id="1e2c2-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="1e2c2-104">按名称删除指定限定符。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1e2c2-105">语法</span><span class="sxs-lookup"><span data-stu-id="1e2c2-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="1e2c2-106">参数</span><span class="sxs-lookup"><span data-stu-id="1e2c2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1e2c2-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1e2c2-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="1e2c2-109">中要删除的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="1e2c2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1e2c2-110">Return value</span></span>

<span data-ttu-id="1e2c2-111">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="1e2c2-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1e2c2-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="1e2c2-112">Constant</span></span>  |<span data-ttu-id="1e2c2-113">值</span><span class="sxs-lookup"><span data-stu-id="1e2c2-113">Value</span></span>  |<span data-ttu-id="1e2c2-114">描述</span><span class="sxs-lookup"><span data-stu-id="1e2c2-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1e2c2-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1e2c2-115">0x80041008</span></span> | <span data-ttu-id="1e2c2-116">`wszName` 参数无效。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="1e2c2-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="1e2c2-117">0x80041016</span></span> | <span data-ttu-id="1e2c2-118">删除此限定符是非法的。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1e2c2-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1e2c2-119">0x80041002</span></span> | <span data-ttu-id="1e2c2-120">找不到指定的限定符。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1e2c2-121">0</span><span class="sxs-lookup"><span data-stu-id="1e2c2-121">0</span></span> | <span data-ttu-id="1e2c2-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="1e2c2-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="1e2c2-123">0x40002</span></span> | <span data-ttu-id="1e2c2-124">已删除本地替代，并且父对象的原始限定符已恢复范围。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1e2c2-125">备注</span><span class="sxs-lookup"><span data-stu-id="1e2c2-125">Remarks</span></span>

<span data-ttu-id="1e2c2-126">此函数包装对[IWbemQualifierSet：:D e)](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="1e2c2-127">由于限定符传播规则，特定限定符可能已从另一个对象继承，并且仅在当前类或实例中被重写。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="1e2c2-128">在这种情况下`QualifierSet_Delete` ，方法会将限定符重置为其原始的继承值。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="1e2c2-129">在这种情况下，函数将返回`WBEM_S_RESET_TO_DEFAULT`状态代码。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e2c2-130">要求</span><span class="sxs-lookup"><span data-stu-id="1e2c2-130">Requirements</span></span>  
 <span data-ttu-id="1e2c2-131">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e2c2-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e2c2-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1e2c2-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1e2c2-133">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1e2c2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e2c2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e2c2-134">See also</span></span>

- [<span data-ttu-id="1e2c2-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="1e2c2-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
