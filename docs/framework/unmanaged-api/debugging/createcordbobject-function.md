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
ms.openlocfilehash: 340d2de09562ea9b767203a7fa839cdc6b729b3b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860894"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="40e3b-102">CreateCordbObject 函数</span><span class="sxs-lookup"><span data-stu-id="40e3b-102">CreateCordbObject Function</span></span>
<span data-ttu-id="40e3b-103">创建一个调试器接口（[ICorDebug](icordebug-interface.md)），该接口提供用于在远程进程中实例化托管调试会话的功能。</span><span class="sxs-lookup"><span data-stu-id="40e3b-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e3b-104">语法</span><span class="sxs-lookup"><span data-stu-id="40e3b-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40e3b-105">参数</span><span class="sxs-lookup"><span data-stu-id="40e3b-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="40e3b-106">[in] 目标进程的调试器版本。</span><span class="sxs-lookup"><span data-stu-id="40e3b-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="40e3b-107">此参数必须为 CorDebugVersion_2_0 以用于远程调试。</span><span class="sxs-lookup"><span data-stu-id="40e3b-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="40e3b-108">弄指向对象的指针的指针，该对象将被强制转换为[ICorDebug](icordebug-interface.md)接口并返回。</span><span class="sxs-lookup"><span data-stu-id="40e3b-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40e3b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="40e3b-109">Return Value</span></span>  
 <span data-ttu-id="40e3b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="40e3b-110">S_OK</span></span>  
 <span data-ttu-id="40e3b-111">已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。</span><span class="sxs-lookup"><span data-stu-id="40e3b-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="40e3b-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="40e3b-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="40e3b-113">`ppCordb` 为 null，或 `iDebuggerVersion` 不是 CorDebugVersion_2_0。</span><span class="sxs-lookup"><span data-stu-id="40e3b-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="40e3b-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="40e3b-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="40e3b-115">无法为 `ppCordb` 分配足够的内存</span><span class="sxs-lookup"><span data-stu-id="40e3b-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="40e3b-116">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="40e3b-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="40e3b-117">其他故障。</span><span class="sxs-lookup"><span data-stu-id="40e3b-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e3b-118">备注</span><span class="sxs-lookup"><span data-stu-id="40e3b-118">Remarks</span></span>  
 <span data-ttu-id="40e3b-119">中[ICorDebug](icordebug-interface.md) `ppCordb`返回的 ICorDebug 接口是所有托管调试服务的顶级调试接口。</span><span class="sxs-lookup"><span data-stu-id="40e3b-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e3b-120">要求</span><span class="sxs-lookup"><span data-stu-id="40e3b-120">Requirements</span></span>  
 <span data-ttu-id="40e3b-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40e3b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e3b-122">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="40e3b-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="40e3b-123">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="40e3b-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="40e3b-124">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="40e3b-124">**.NET Framework Versions:** 3.5 SP1</span></span>
