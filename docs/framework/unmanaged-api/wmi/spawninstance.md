---
title: SpawnInstance 函数 （非托管 API 参考）
description: SpawnInstance 函数创建一个类的新实例。
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8056ef18089f56f1f9b6717d505fa3d058957541
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074412"
---
# <a name="spawninstance-function"></a><span data-ttu-id="5f48a-103">SpawnInstance 函数</span><span class="sxs-lookup"><span data-stu-id="5f48a-103">SpawnInstance function</span></span>
<span data-ttu-id="5f48a-104">创建类的新实例。</span><span class="sxs-lookup"><span data-stu-id="5f48a-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5f48a-105">语法</span><span class="sxs-lookup"><span data-stu-id="5f48a-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="5f48a-106">参数</span><span class="sxs-lookup"><span data-stu-id="5f48a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5f48a-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="5f48a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5f48a-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="5f48a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="5f48a-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="5f48a-109">[in] Reserved.</span></span> <span data-ttu-id="5f48a-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="5f48a-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="5f48a-111">[out]接收到的类的新实例的指针。</span><span class="sxs-lookup"><span data-stu-id="5f48a-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="5f48a-112">如果发生错误，新对象不是返回，和`ppNewInstance`左侧不被修改。</span><span class="sxs-lookup"><span data-stu-id="5f48a-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="5f48a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="5f48a-113">Return value</span></span>

<span data-ttu-id="5f48a-114">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="5f48a-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5f48a-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="5f48a-115">Constant</span></span>  |<span data-ttu-id="5f48a-116">“值”</span><span class="sxs-lookup"><span data-stu-id="5f48a-116">Value</span></span>  |<span data-ttu-id="5f48a-117">描述</span><span class="sxs-lookup"><span data-stu-id="5f48a-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="5f48a-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="5f48a-118">0x80041020</span></span> | `ptr` <span data-ttu-id="5f48a-119">不是有效的类定义，无法生成新的实例。</span><span class="sxs-lookup"><span data-stu-id="5f48a-119">is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="5f48a-120">不完整，或者它尚未注册到 Windows 管理通过调用[PutClassWmi](putclasswmi.md)。</span><span class="sxs-lookup"><span data-stu-id="5f48a-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5f48a-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5f48a-121">0x80041006</span></span> | <span data-ttu-id="5f48a-122">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="5f48a-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5f48a-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5f48a-123">0x80041008</span></span> | `ppNewClass` <span data-ttu-id="5f48a-124">是`null`。</span><span class="sxs-lookup"><span data-stu-id="5f48a-124">is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5f48a-125">0</span><span class="sxs-lookup"><span data-stu-id="5f48a-125">0</span></span> | <span data-ttu-id="5f48a-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="5f48a-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5f48a-127">备注</span><span class="sxs-lookup"><span data-stu-id="5f48a-127">Remarks</span></span>

<span data-ttu-id="5f48a-128">此函数包装对的调用[IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)方法。</span><span class="sxs-lookup"><span data-stu-id="5f48a-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

`ptr` <span data-ttu-id="5f48a-129">必须在类定义获取从 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="5f48a-129">must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="5f48a-130">（请注意，支持生成实例中的实例，但返回的实例为空。）然后可以使用此类定义创建新实例。</span><span class="sxs-lookup"><span data-stu-id="5f48a-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="5f48a-131">调用[PutInstanceWmi](putinstancewmi.md)函数是必需的如果你想要将实例写入 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="5f48a-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="5f48a-132">新的对象中返回`ppNewClass`自动成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="5f48a-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="5f48a-133">不能重写此行为。</span><span class="sxs-lookup"><span data-stu-id="5f48a-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="5f48a-134">没有其他方法可以创建子类 （的派生类）。</span><span class="sxs-lookup"><span data-stu-id="5f48a-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f48a-135">要求</span><span class="sxs-lookup"><span data-stu-id="5f48a-135">Requirements</span></span>  
 <span data-ttu-id="5f48a-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f48a-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f48a-137">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5f48a-137">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="5f48a-138">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5f48a-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f48a-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f48a-139">See also</span></span>

- [<span data-ttu-id="5f48a-140">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="5f48a-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
