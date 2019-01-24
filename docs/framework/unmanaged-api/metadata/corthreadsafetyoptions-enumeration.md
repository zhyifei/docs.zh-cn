---
title: CorThreadSafetyOptions 枚举
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b460c2c4b0d38ec46ee9d7341de9b320a2ecaa7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594637"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="df9bd-102">CorThreadSafetyOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="df9bd-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="df9bd-103">指定用于选择线程安全性选项的标志。</span><span class="sxs-lookup"><span data-stu-id="df9bd-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df9bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="df9bd-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="df9bd-105">成员</span><span class="sxs-lookup"><span data-stu-id="df9bd-105">Members</span></span>  
  
|<span data-ttu-id="df9bd-106">成员</span><span class="sxs-lookup"><span data-stu-id="df9bd-106">Member</span></span>|<span data-ttu-id="df9bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="df9bd-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="df9bd-108">默认值。</span><span class="sxs-lookup"><span data-stu-id="df9bd-108">Default value.</span></span> <span data-ttu-id="df9bd-109">与 `MDThreadSatetyOff` 相同。</span><span class="sxs-lookup"><span data-stu-id="df9bd-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="df9bd-110">指示不能设置读取器/写入器锁。</span><span class="sxs-lookup"><span data-stu-id="df9bd-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="df9bd-111">指示可以设置读取器/写入器锁。</span><span class="sxs-lookup"><span data-stu-id="df9bd-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df9bd-112">要求</span><span class="sxs-lookup"><span data-stu-id="df9bd-112">Requirements</span></span>  
 <span data-ttu-id="df9bd-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df9bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df9bd-114">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="df9bd-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="df9bd-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df9bd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9bd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="df9bd-116">See also</span></span>
- [<span data-ttu-id="df9bd-117">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="df9bd-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
