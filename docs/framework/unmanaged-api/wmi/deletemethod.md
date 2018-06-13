---
title: Delete 方法函数 （非托管 API 参考）
description: Delete 方法函数从 CIM 类定义中删除指定的方法。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd862910d0c9bb0274158c2c516211cef598a553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457803"
---
# <a name="deletemethod-function"></a><span data-ttu-id="bef52-103">Delete 方法函数</span><span class="sxs-lookup"><span data-stu-id="bef52-103">DeleteMethod function</span></span>
<span data-ttu-id="bef52-104">从 CIM 类定义中删除指定的方法。</span><span class="sxs-lookup"><span data-stu-id="bef52-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="bef52-105">语法</span><span class="sxs-lookup"><span data-stu-id="bef52-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="bef52-106">参数</span><span class="sxs-lookup"><span data-stu-id="bef52-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bef52-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="bef52-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bef52-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="bef52-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="bef52-109">[in]要从类表中移除的方法名称。</span><span class="sxs-lookup"><span data-stu-id="bef52-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="bef52-110">`wszName` 必须为有效的指针`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="bef52-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="bef52-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bef52-111">Return value</span></span>

<span data-ttu-id="bef52-112">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="bef52-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bef52-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bef52-113">Constant</span></span>  |<span data-ttu-id="bef52-114">值</span><span class="sxs-lookup"><span data-stu-id="bef52-114">Value</span></span>  |<span data-ttu-id="bef52-115">描述</span><span class="sxs-lookup"><span data-stu-id="bef52-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="bef52-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="bef52-116">0x80041002</span></span> | <span data-ttu-id="bef52-117">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="bef52-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bef52-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bef52-118">0x80041006</span></span> | <span data-ttu-id="bef52-119">没有足够的内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bef52-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bef52-120">0</span><span class="sxs-lookup"><span data-stu-id="bef52-120">0</span></span> | <span data-ttu-id="bef52-121">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="bef52-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="bef52-122">备注</span><span class="sxs-lookup"><span data-stu-id="bef52-122">Remarks</span></span>

<span data-ttu-id="bef52-123">此函数包装对的调用[IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="bef52-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="bef52-124">不支持方法删除[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向 CIM 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="bef52-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="bef52-125">要求</span><span class="sxs-lookup"><span data-stu-id="bef52-125">Requirements</span></span>  
 <span data-ttu-id="bef52-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bef52-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef52-127">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bef52-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bef52-128">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bef52-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef52-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="bef52-129">See also</span></span>  
[<span data-ttu-id="bef52-130">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bef52-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
