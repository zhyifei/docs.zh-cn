---
title: ILCodeKind 枚举
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fa7d06f39dc05da6fd1657404f882c14c44ea9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505012"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="290be-102">ILCodeKind 枚举</span><span class="sxs-lookup"><span data-stu-id="290be-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="290be-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="290be-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="290be-104">提供用于指定调试器是否能够访问在探查器 ReJIT 检测中添加的局部变量或代码的值。</span><span class="sxs-lookup"><span data-stu-id="290be-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290be-105">语法</span><span class="sxs-lookup"><span data-stu-id="290be-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="290be-106">成员</span><span class="sxs-lookup"><span data-stu-id="290be-106">Members</span></span>  
  
|<span data-ttu-id="290be-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="290be-107">Member name</span></span>|<span data-ttu-id="290be-108">描述</span><span class="sxs-lookup"><span data-stu-id="290be-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="290be-109">调试器无法访问 ReJIT 检测的信息。</span><span class="sxs-lookup"><span data-stu-id="290be-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="290be-110">调试器可以访问 ReJIT 检测的信息。</span><span class="sxs-lookup"><span data-stu-id="290be-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="290be-111">备注</span><span class="sxs-lookup"><span data-stu-id="290be-111">Remarks</span></span>  
 <span data-ttu-id="290be-112">成员`ILCodeKind`枚举可以传递给[EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)并[GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)方法来确定调试器是否可以访问在探查器中添加的变量ReJIT 检测中，并对其[GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)方法，以确定调试器是否可以访问检测到的 IL。</span><span class="sxs-lookup"><span data-stu-id="290be-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="290be-113">要求</span><span class="sxs-lookup"><span data-stu-id="290be-113">Requirements</span></span>  
 <span data-ttu-id="290be-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="290be-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="290be-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="290be-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="290be-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="290be-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="290be-117">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="290be-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="290be-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="290be-118">See also</span></span>
- [<span data-ttu-id="290be-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="290be-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="290be-120">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="290be-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="290be-121">ReJIT:操作方法指南</span><span class="sxs-lookup"><span data-stu-id="290be-121">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
