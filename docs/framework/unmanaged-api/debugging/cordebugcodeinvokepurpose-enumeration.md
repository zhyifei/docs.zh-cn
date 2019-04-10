---
title: “Cor调试代码调用目的”枚举
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 858dfe9b15422680a261fef9e22d8c89d9d7fe45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155566"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="65b79-102">“Cor调试代码调用目的”枚举</span><span class="sxs-lookup"><span data-stu-id="65b79-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="65b79-103">描述为何导出的函数会调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="65b79-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b79-104">语法</span><span class="sxs-lookup"><span data-stu-id="65b79-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="65b79-105">成员</span><span class="sxs-lookup"><span data-stu-id="65b79-105">Members</span></span>  
  
|<span data-ttu-id="65b79-106">成员</span><span class="sxs-lookup"><span data-stu-id="65b79-106">Member</span></span>|<span data-ttu-id="65b79-107">描述</span><span class="sxs-lookup"><span data-stu-id="65b79-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="65b79-108">无或未知。</span><span class="sxs-lookup"><span data-stu-id="65b79-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="65b79-109">托管代码会运行所有的托管入口点，例如反向平台调用 (p-invoke)。</span><span class="sxs-lookup"><span data-stu-id="65b79-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="65b79-110">通过运行时间无法得知更多目的。</span><span class="sxs-lookup"><span data-stu-id="65b79-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="65b79-111">托管代码会运行一个静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="65b79-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="65b79-112">托管代码会运行一些受调用的接口方法的实施。</span><span class="sxs-lookup"><span data-stu-id="65b79-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65b79-113">备注</span><span class="sxs-lookup"><span data-stu-id="65b79-113">Remarks</span></span>  
 <span data-ttu-id="65b79-114">此枚举由[ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)方法以提供信息通过单步执行托管代码。</span><span class="sxs-lookup"><span data-stu-id="65b79-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b79-115">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="65b79-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b79-116">要求</span><span class="sxs-lookup"><span data-stu-id="65b79-116">Requirements</span></span>  
 <span data-ttu-id="65b79-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65b79-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b79-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65b79-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65b79-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65b79-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="65b79-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="65b79-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65b79-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="65b79-121">See also</span></span>

- [<span data-ttu-id="65b79-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="65b79-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="65b79-123">调试</span><span class="sxs-lookup"><span data-stu-id="65b79-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
