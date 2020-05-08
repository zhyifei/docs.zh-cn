---
title: ICorDebugComObjectValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 528db447df4d71d67441b05ad29e6a900c59afbb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892825"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="2ed03-102">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="2ed03-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="2ed03-103">提供用于检索与运行时可调用包装（RCW）关联的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="2ed03-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ed03-104">方法</span><span class="sxs-lookup"><span data-stu-id="2ed03-104">Methods</span></span>  
  
|<span data-ttu-id="2ed03-105">方法</span><span class="sxs-lookup"><span data-stu-id="2ed03-105">Method</span></span>|<span data-ttu-id="2ed03-106">说明</span><span class="sxs-lookup"><span data-stu-id="2ed03-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ed03-107">GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="2ed03-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="2ed03-108">获取缓存在当前 RCW 上的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="2ed03-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="2ed03-109">GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="2ed03-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="2ed03-110">为当前对象的大小写或用作的接口类型提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="2ed03-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ed03-111">备注</span><span class="sxs-lookup"><span data-stu-id="2ed03-111">Remarks</span></span>  
 <span data-ttu-id="2ed03-112">若要检查 "ICorDebugValue" 接口的实例是否表示 RCW，调试程序使用`QueryInterface` `IID_ICorDebugComObjectValue`"ICorDebugValue" 调用。</span><span class="sxs-lookup"><span data-stu-id="2ed03-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed03-113">要求</span><span class="sxs-lookup"><span data-stu-id="2ed03-113">Requirements</span></span>  
 <span data-ttu-id="2ed03-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ed03-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed03-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ed03-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ed03-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ed03-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ed03-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed03-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed03-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ed03-118">See also</span></span>

- [<span data-ttu-id="2ed03-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="2ed03-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2ed03-120">调试</span><span class="sxs-lookup"><span data-stu-id="2ed03-120">Debugging</span></span>](index.md)
