---
title: CreateCordbObject 函数
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 1d190c5b558c7c523be09267e59eab7c5611563a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793856"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="2b06d-102">CreateCordbObject 函数</span><span class="sxs-lookup"><span data-stu-id="2b06d-102">CreateCordbObject Function</span></span>
<span data-ttu-id="2b06d-103">创建一个调试器接口（[ICorDebug](icordebug-interface.md)），该接口提供用于在远程进程中实例化托管调试会话的功能。</span><span class="sxs-lookup"><span data-stu-id="2b06d-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b06d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b06d-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b06d-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b06d-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="2b06d-106">[in] 目标进程的调试器版本。</span><span class="sxs-lookup"><span data-stu-id="2b06d-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="2b06d-107">此参数必须为 CorDebugVersion_2_0 以用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="2b06d-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="2b06d-108">弄指向对象的指针的指针，该对象将被强制转换为[ICorDebug](icordebug-interface.md)接口并返回。</span><span class="sxs-lookup"><span data-stu-id="2b06d-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b06d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2b06d-109">Return Value</span></span>  
 <span data-ttu-id="2b06d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b06d-110">S_OK</span></span>  
 <span data-ttu-id="2b06d-111">已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。</span><span class="sxs-lookup"><span data-stu-id="2b06d-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="2b06d-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2b06d-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="2b06d-113">`ppCordb` 为 null，或 `iDebuggerVersion` 不是 CorDebugVersion_2_0。</span><span class="sxs-lookup"><span data-stu-id="2b06d-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="2b06d-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2b06d-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2b06d-115">无法为 `ppCordb` 分配足够的内存</span><span class="sxs-lookup"><span data-stu-id="2b06d-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="2b06d-116">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="2b06d-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2b06d-117">其他故障。</span><span class="sxs-lookup"><span data-stu-id="2b06d-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b06d-118">备注</span><span class="sxs-lookup"><span data-stu-id="2b06d-118">Remarks</span></span>  
 <span data-ttu-id="2b06d-119">`ppCordb` 中返回的[ICorDebug](icordebug-interface.md)接口是所有托管调试服务的顶级调试接口。</span><span class="sxs-lookup"><span data-stu-id="2b06d-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b06d-120">需求</span><span class="sxs-lookup"><span data-stu-id="2b06d-120">Requirements</span></span>  
 <span data-ttu-id="2b06d-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b06d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b06d-122">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="2b06d-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2b06d-123">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="2b06d-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2b06d-124">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2b06d-124">**.NET Framework Versions:** 3.5 SP1</span></span>
