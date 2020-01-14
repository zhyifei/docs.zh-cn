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
ms.openlocfilehash: 553a92812f009ca1033f1bdcda0ea3722c5f01e3
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937837"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="47c05-102">ILCodeKind 枚举</span><span class="sxs-lookup"><span data-stu-id="47c05-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="47c05-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="47c05-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="47c05-104">提供用于指定调试器是否能够访问在探查器 ReJIT 检测中添加的局部变量或代码的值。</span><span class="sxs-lookup"><span data-stu-id="47c05-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c05-105">语法</span><span class="sxs-lookup"><span data-stu-id="47c05-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="47c05-106">Members</span><span class="sxs-lookup"><span data-stu-id="47c05-106">Members</span></span>  
  
|<span data-ttu-id="47c05-107">成员名称</span><span class="sxs-lookup"><span data-stu-id="47c05-107">Member name</span></span>|<span data-ttu-id="47c05-108">描述</span><span class="sxs-lookup"><span data-stu-id="47c05-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="47c05-109">调试器无法访问 ReJIT 检测的信息。</span><span class="sxs-lookup"><span data-stu-id="47c05-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="47c05-110">调试器可以访问 ReJIT 检测的信息。</span><span class="sxs-lookup"><span data-stu-id="47c05-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47c05-111">备注</span><span class="sxs-lookup"><span data-stu-id="47c05-111">Remarks</span></span>  
 <span data-ttu-id="47c05-112">`ILCodeKind` 枚举的成员可以传递给[EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)和[GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)方法，以确定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和[GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)方法，以确定调试器是否可以访问已检测的 IL。</span><span class="sxs-lookup"><span data-stu-id="47c05-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c05-113">需求</span><span class="sxs-lookup"><span data-stu-id="47c05-113">Requirements</span></span>  
 <span data-ttu-id="47c05-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47c05-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c05-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47c05-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47c05-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47c05-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47c05-117">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c05-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c05-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47c05-118">See also</span></span>

- [<span data-ttu-id="47c05-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="47c05-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="47c05-120">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="47c05-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="47c05-121">ReJIT：操作方法指南</span><span class="sxs-lookup"><span data-stu-id="47c05-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
