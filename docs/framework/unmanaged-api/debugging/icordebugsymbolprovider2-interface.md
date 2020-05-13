---
title: ICorDebugSymbolProvider2 接口
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379291"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="74651-102">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="74651-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="74651-103">以逻辑方式扩展[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)接口以检索其他调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="74651-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74651-104">方法</span><span class="sxs-lookup"><span data-stu-id="74651-104">Methods</span></span>  
  
|<span data-ttu-id="74651-105">方法</span><span class="sxs-lookup"><span data-stu-id="74651-105">Method</span></span>|<span data-ttu-id="74651-106">描述</span><span class="sxs-lookup"><span data-stu-id="74651-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74651-107">GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="74651-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="74651-108">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="74651-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="74651-109">GetGenericDictionaryInfo 方法</span><span class="sxs-lookup"><span data-stu-id="74651-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="74651-110">检索泛型字典映射。</span><span class="sxs-lookup"><span data-stu-id="74651-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74651-111">备注</span><span class="sxs-lookup"><span data-stu-id="74651-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74651-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="74651-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="74651-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="74651-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74651-114">要求</span><span class="sxs-lookup"><span data-stu-id="74651-114">Requirements</span></span>  
 <span data-ttu-id="74651-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74651-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74651-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74651-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74651-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74651-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74651-118">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74651-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74651-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="74651-119">See also</span></span>

- [<span data-ttu-id="74651-120">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="74651-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="74651-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="74651-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="74651-122">调试</span><span class="sxs-lookup"><span data-stu-id="74651-122">Debugging</span></span>](index.md)
