---
title: "“Cor调试记录格式”枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRecordFormat
api_location: mscordbi.dll
api_type: COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c2f8397382dde061078a0d96114420f1c5f48669
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="724c3-102">“Cor调试记录格式”枚举</span><span class="sxs-lookup"><span data-stu-id="724c3-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="724c3-103">描述包含本机异常调试事件相关信息的字节数组的数据格式。</span><span class="sxs-lookup"><span data-stu-id="724c3-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="724c3-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="724c3-105">成员</span><span class="sxs-lookup"><span data-stu-id="724c3-105">Members</span></span>  
  
|<span data-ttu-id="724c3-106">成员</span><span class="sxs-lookup"><span data-stu-id="724c3-106">Member</span></span>|<span data-ttu-id="724c3-107">描述</span><span class="sxs-lookup"><span data-stu-id="724c3-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="724c3-108">数据为 32 位 Windows 异常记录。</span><span class="sxs-lookup"><span data-stu-id="724c3-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="724c3-109">数据为 64 位 Windows 异常记录。</span><span class="sxs-lookup"><span data-stu-id="724c3-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="724c3-110">备注</span><span class="sxs-lookup"><span data-stu-id="724c3-110">Remarks</span></span>  
 <span data-ttu-id="724c3-111">成员`CorDebugRecordFormat`枚举传递给[解码事件](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法，以指示中的字节数组格式其`pRecord`自变量。</span><span class="sxs-lookup"><span data-stu-id="724c3-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="724c3-112">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="724c3-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724c3-113">要求</span><span class="sxs-lookup"><span data-stu-id="724c3-113">Requirements</span></span>  
 <span data-ttu-id="724c3-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="724c3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724c3-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="724c3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="724c3-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="724c3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="724c3-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="724c3-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724c3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="724c3-118">See Also</span></span>  
 [<span data-ttu-id="724c3-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="724c3-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
