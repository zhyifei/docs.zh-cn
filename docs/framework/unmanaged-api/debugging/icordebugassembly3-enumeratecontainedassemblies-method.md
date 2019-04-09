---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 方法
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080951"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="d1fb1-102">ICorDebugAssembly3::EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="d1fb1-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="d1fb1-103">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1fb1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1fb1-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1fb1-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1fb1-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="d1fb1-106">[out]指向一个 ICorDebugAssemblyEnum 接口对象，它枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1fb1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d1fb1-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="d1fb1-108">如果此`ICorDebugAssembly3`对象是一个容器; 否则为`S_FALSE`，枚举为空。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-108">if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1fb1-109">备注</span><span class="sxs-lookup"><span data-stu-id="d1fb1-109">Remarks</span></span>  
 <span data-ttu-id="d1fb1-110">需用符号来列举包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="d1fb1-111">如果其并不存在，则方法返回 `S_FALSE`，且不提供有效枚举。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1fb1-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1fb1-113">要求</span><span class="sxs-lookup"><span data-stu-id="d1fb1-113">Requirements</span></span>  
 <span data-ttu-id="d1fb1-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fb1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1fb1-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1fb1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1fb1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1fb1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d1fb1-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d1fb1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1fb1-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1fb1-118">See also</span></span>

- [<span data-ttu-id="d1fb1-119">“ICor调试程序集3”接口</span><span class="sxs-lookup"><span data-stu-id="d1fb1-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="d1fb1-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="d1fb1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
