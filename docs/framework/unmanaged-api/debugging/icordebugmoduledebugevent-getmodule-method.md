---
title: ICorDebugModuleDebugEvent::GetModule 方法
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 4d9eea8fb5c42002763a0ae52a186bf2c1e6d2ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792909"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="8d1d3-102">ICorDebugModuleDebugEvent::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="8d1d3-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="8d1d3-103">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="8d1d3-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d1d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d1d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d1d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d1d3-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="8d1d3-106">[out] 指向 ICorDebugModule 对象地址的指针，该对象表示刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="8d1d3-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d1d3-107">备注</span><span class="sxs-lookup"><span data-stu-id="8d1d3-107">Remarks</span></span>  
 <span data-ttu-id="8d1d3-108">可以调用[GetEventKind](icordebugdebugevent-geteventkind-method.md)方法来确定是加载还是卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="8d1d3-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d1d3-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="8d1d3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d1d3-110">需求</span><span class="sxs-lookup"><span data-stu-id="8d1d3-110">Requirements</span></span>  
 <span data-ttu-id="8d1d3-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d1d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d1d3-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d1d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d1d3-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d1d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d1d3-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d1d3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1d3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d1d3-115">See also</span></span>

- [<span data-ttu-id="8d1d3-116">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="8d1d3-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="8d1d3-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="8d1d3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
