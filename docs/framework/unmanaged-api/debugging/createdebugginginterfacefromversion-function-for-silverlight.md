---
title: Silverlight 的 CreateDebuggingInterfaceFromVersion 函数
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: f40345b09cae164660711b987f62130518736518
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208619"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="d3d4d-102">Silverlight 的 CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="d3d4d-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>

<span data-ttu-id="d3d4d-103">接受从[CreateVersionStringFromModule 函数](createversionstringfrommodule-function.md)返回的公共语言运行时（CLR）版本字符串，并返回相应的调试器接口（通常为[ICorDebug](icordebug-interface.md)）。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3d4d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3d4d-105">Parameters</span></span>  

 `szDebuggeeVersion`\
 <span data-ttu-id="d3d4d-106">中目标调试对象（由[CreateVersionStringFromModule 函数](createversionstringfrommodule-function.md)返回）中的 CLR 的版本字符串。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`\
 <span data-ttu-id="d3d4d-107">[out] 指向“COM 对象的指针”的指针 (`IUnknown`)。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="d3d4d-108">此对象将在返回之前强制转换为[ICorDebug](icordebug-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3d4d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d3d4d-109">Return Value</span></span>

 `S_OK`\
 <span data-ttu-id="d3d4d-110">`ppCordb`引用实现[ICorDebug 接口](icordebug-interface.md)接口的有效对象。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-110">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 `E_INVALIDARG`\
 <span data-ttu-id="d3d4d-111">`szDebuggeeVersion` 或 `ppCordb` 为 null。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-111">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 <span data-ttu-id="d3d4d-112">找不到 CLR 调试所需的组件。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-112">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="d3d4d-113">在与目标 CoreCLR 相同的目录中找不到_mscordbi.dll_或_mscordaccore.dll_ 。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-113">Either _mscordbi.dll_ or _mscordaccore.dll_ was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 <span data-ttu-id="d3d4d-114">mscordbi.dll 或 mscordaccore.dll 与目标 CoreCLR.dll 版本不一致。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-114">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="d3d4d-115">`E_FAIL`（或其他 `E_` 返回代码） </span><span class="sxs-lookup"><span data-stu-id="d3d4d-115">`E_FAIL` (or other `E_` return codes)</span></span>\
 <span data-ttu-id="d3d4d-116">无法返回[ICorDebug 接口](icordebug-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-116">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3d4d-117">备注</span><span class="sxs-lookup"><span data-stu-id="d3d4d-117">Remarks</span></span>

 <span data-ttu-id="d3d4d-118">返回的接口提供用于附加到目标进程中的 CLR 和调试 CLR 正在运行的托管代码的功能。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-118">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d4d-119">要求</span><span class="sxs-lookup"><span data-stu-id="d3d4d-119">Requirements</span></span>

 <span data-ttu-id="d3d4d-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d4d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d4d-121">**标头：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="d3d4d-121">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="d3d4d-122">**库：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="d3d4d-122">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="d3d4d-123">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d3d4d-123">**.NET Framework Versions:** 3.5 SP1</span></span>
