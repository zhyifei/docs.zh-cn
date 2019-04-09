---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94e2f1c13c91c50daa5730898adf0aedf00f6579
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092612"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="a5dae-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode 方法</span><span class="sxs-lookup"><span data-stu-id="a5dae-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="a5dae-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="a5dae-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a5dae-104">配置调试器如何处理目标进程中元数据的内存中更新。</span><span class="sxs-lookup"><span data-stu-id="a5dae-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5dae-105">语法</span><span class="sxs-lookup"><span data-stu-id="a5dae-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5dae-106">参数</span><span class="sxs-lookup"><span data-stu-id="a5dae-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="a5dae-107">一个[WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)枚举值，该值指定目标进程中元数据的内存中更新是否可见 (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) 或不可见 (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) 到调试器。</span><span class="sxs-lookup"><span data-stu-id="a5dae-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5dae-108">备注</span><span class="sxs-lookup"><span data-stu-id="a5dae-108">Remarks</span></span>  
 <span data-ttu-id="a5dae-109">目标进程中元数据的更新可以来自于“编辑并继续”、探查器或 <xref:System.Reflection.Emit?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a5dae-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5dae-110">要求</span><span class="sxs-lookup"><span data-stu-id="a5dae-110">Requirements</span></span>  
 <span data-ttu-id="a5dae-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5dae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5dae-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5dae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5dae-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5dae-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a5dae-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a5dae-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5dae-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5dae-115">See also</span></span>

- [<span data-ttu-id="a5dae-116">ICorDebugProcess7 接口</span><span class="sxs-lookup"><span data-stu-id="a5dae-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)
- [<span data-ttu-id="a5dae-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a5dae-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
