---
title: ICorDebugAppDomainEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 9fb849c78636d5e29f58a70f59aa4cb3cd22df40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784737"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="965ea-102">ICorDebugAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="965ea-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="965ea-103">提供 `Next` 方法，该方法从枚举中的下一个位置开始返回指定数目的 `ICorDebugAppDomainEnum` 值。</span><span class="sxs-lookup"><span data-stu-id="965ea-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="965ea-104">此接口是 "ICorDebugEnum" 的子类。</span><span class="sxs-lookup"><span data-stu-id="965ea-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="965ea-105">方法</span><span class="sxs-lookup"><span data-stu-id="965ea-105">Methods</span></span>  
  
|<span data-ttu-id="965ea-106">方法</span><span class="sxs-lookup"><span data-stu-id="965ea-106">Method</span></span>|<span data-ttu-id="965ea-107">描述</span><span class="sxs-lookup"><span data-stu-id="965ea-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="965ea-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="965ea-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="965ea-109">从当前游标位置开始，获取集合中指定数量的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="965ea-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="965ea-110">备注</span><span class="sxs-lookup"><span data-stu-id="965ea-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="965ea-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="965ea-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="965ea-112">需求</span><span class="sxs-lookup"><span data-stu-id="965ea-112">Requirements</span></span>  
 <span data-ttu-id="965ea-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="965ea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="965ea-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="965ea-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="965ea-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="965ea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="965ea-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="965ea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="965ea-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="965ea-117">See also</span></span>

- [<span data-ttu-id="965ea-118">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="965ea-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="965ea-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="965ea-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
