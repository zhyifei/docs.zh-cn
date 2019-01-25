---
title: ICorDebugType2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f61efdecfb87ed598dd9675c0b8804259849e64c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706255"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="d6357-102">ICorDebugType2 接口</span><span class="sxs-lookup"><span data-stu-id="d6357-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="d6357-103">扩展 ICorDebugType 接口可检索的基类型或复杂 （用户定义的） 类型的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="d6357-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6357-104">方法</span><span class="sxs-lookup"><span data-stu-id="d6357-104">Methods</span></span>  
  
|<span data-ttu-id="d6357-105">方法</span><span class="sxs-lookup"><span data-stu-id="d6357-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="d6357-106">GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="d6357-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="d6357-107">获取[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)此类型。</span><span class="sxs-lookup"><span data-stu-id="d6357-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6357-108">备注</span><span class="sxs-lookup"><span data-stu-id="d6357-108">Remarks</span></span>  
 <span data-ttu-id="d6357-109">此接口是 ICorDebugType 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="d6357-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6357-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d6357-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6357-111">示例</span><span class="sxs-lookup"><span data-stu-id="d6357-111">Example</span></span>  
 <span data-ttu-id="d6357-112">下面的代码段演示如何使用[ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d6357-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="d6357-113">要求</span><span class="sxs-lookup"><span data-stu-id="d6357-113">Requirements</span></span>  
 <span data-ttu-id="d6357-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6357-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6357-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6357-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6357-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6357-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6357-117">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6357-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6357-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6357-118">See also</span></span>
- [<span data-ttu-id="d6357-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="d6357-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
