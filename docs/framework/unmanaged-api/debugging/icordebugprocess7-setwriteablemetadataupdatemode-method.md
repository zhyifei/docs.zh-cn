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
ms.openlocfilehash: 6de75e1e27660ac91bd6320a501db47f3b055fb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212251"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="24e30-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode 方法</span><span class="sxs-lookup"><span data-stu-id="24e30-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="24e30-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="24e30-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="24e30-104">配置调试器如何处理目标进程中元数据的内存中更新。</span><span class="sxs-lookup"><span data-stu-id="24e30-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e30-105">语法</span><span class="sxs-lookup"><span data-stu-id="24e30-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24e30-106">参数</span><span class="sxs-lookup"><span data-stu-id="24e30-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="24e30-107">一个[WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md)枚举值，该值指定目标进程中的元数据的内存中更新对调试器是否可见（ `WriteableMetadataUpdateMode::AlwaysShowUpdates` ）或不可见（ `WriteableMetadataUpdateMode::LegacyCompatPolicy` ）。</span><span class="sxs-lookup"><span data-stu-id="24e30-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24e30-108">备注</span><span class="sxs-lookup"><span data-stu-id="24e30-108">Remarks</span></span>  
 <span data-ttu-id="24e30-109">目标进程中元数据的更新可以来自于“编辑并继续”、探查器或 <xref:System.Reflection.Emit?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="24e30-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e30-110">要求</span><span class="sxs-lookup"><span data-stu-id="24e30-110">Requirements</span></span>  
 <span data-ttu-id="24e30-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24e30-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24e30-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24e30-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24e30-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24e30-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24e30-114">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24e30-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e30-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="24e30-115">See also</span></span>

- [<span data-ttu-id="24e30-116">ICorDebugProcess7 接口</span><span class="sxs-lookup"><span data-stu-id="24e30-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="24e30-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="24e30-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
