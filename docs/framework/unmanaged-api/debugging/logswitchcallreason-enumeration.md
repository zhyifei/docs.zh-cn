---
title: LogSwitchCallReason 枚举
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eadb595eb62b4f1a9dcc888225cbb7454119c7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198486"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="0dd8a-102">LogSwitchCallReason 枚举</span><span class="sxs-lookup"><span data-stu-id="0dd8a-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="0dd8a-103">指示已对调试/跟踪开关执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0dd8a-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0dd8a-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="0dd8a-105">成员</span><span class="sxs-lookup"><span data-stu-id="0dd8a-105">Members</span></span>  
  
|<span data-ttu-id="0dd8a-106">成员</span><span class="sxs-lookup"><span data-stu-id="0dd8a-106">Member</span></span>|<span data-ttu-id="0dd8a-107">描述</span><span class="sxs-lookup"><span data-stu-id="0dd8a-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="0dd8a-108">创建调试/跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="0dd8a-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="0dd8a-109">调试/跟踪开关进行了修改。</span><span class="sxs-lookup"><span data-stu-id="0dd8a-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="0dd8a-110">调试/跟踪开关已删除。</span><span class="sxs-lookup"><span data-stu-id="0dd8a-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dd8a-111">要求</span><span class="sxs-lookup"><span data-stu-id="0dd8a-111">Requirements</span></span>  
 <span data-ttu-id="0dd8a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd8a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd8a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dd8a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dd8a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dd8a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0dd8a-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0dd8a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0dd8a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dd8a-116">See also</span></span>

- [<span data-ttu-id="0dd8a-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="0dd8a-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
