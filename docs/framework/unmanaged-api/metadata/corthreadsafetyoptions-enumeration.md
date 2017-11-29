---
title: "CorThreadSafetyOptions 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorThreadSafetyOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorThreadSafetyOptions
helpviewer_keywords: CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccdd7fb2b97e98227a581b3b97783c2c47bcab1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="0105b-102">CorThreadSafetyOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="0105b-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="0105b-103">指定用于选择线程安全性选项的标志。</span><span class="sxs-lookup"><span data-stu-id="0105b-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0105b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0105b-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="0105b-105">成员</span><span class="sxs-lookup"><span data-stu-id="0105b-105">Members</span></span>  
  
|<span data-ttu-id="0105b-106">成员</span><span class="sxs-lookup"><span data-stu-id="0105b-106">Member</span></span>|<span data-ttu-id="0105b-107">描述</span><span class="sxs-lookup"><span data-stu-id="0105b-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="0105b-108">默认值。</span><span class="sxs-lookup"><span data-stu-id="0105b-108">Default value.</span></span> <span data-ttu-id="0105b-109">与 `MDThreadSatetyOff` 相同。</span><span class="sxs-lookup"><span data-stu-id="0105b-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="0105b-110">指示读取器/编写器锁不能设置。</span><span class="sxs-lookup"><span data-stu-id="0105b-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="0105b-111">指示可以设置读取器/编写器锁定。</span><span class="sxs-lookup"><span data-stu-id="0105b-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0105b-112">要求</span><span class="sxs-lookup"><span data-stu-id="0105b-112">Requirements</span></span>  
 <span data-ttu-id="0105b-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0105b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0105b-114">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0105b-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0105b-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0105b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0105b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0105b-116">See Also</span></span>  
 [<span data-ttu-id="0105b-117">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="0105b-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
