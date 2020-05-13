---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: d118f0c984663e0844783ff52859698dd5335058
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376137"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="4f263-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="4f263-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="4f263-103">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="4f263-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f263-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f263-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f263-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f263-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="4f263-106">弄指向[ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)对象地址的指针，该对象包含有关合并的程序集元数据的大小和地址的信息。</span><span class="sxs-lookup"><span data-stu-id="4f263-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f263-107">备注</span><span class="sxs-lookup"><span data-stu-id="4f263-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f263-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="4f263-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f263-109">要求</span><span class="sxs-lookup"><span data-stu-id="4f263-109">Requirements</span></span>  
 <span data-ttu-id="4f263-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f263-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f263-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f263-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f263-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f263-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f263-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f263-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f263-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f263-114">See also</span></span>

- [<span data-ttu-id="4f263-115">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="4f263-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4f263-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="4f263-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
