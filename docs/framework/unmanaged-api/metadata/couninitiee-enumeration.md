---
title: COUNINITIEE 枚举
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045053"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="9ced0-102">COUNINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="9ced0-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="9ced0-103">指定使用的常量[CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)初始化公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="9ced0-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ced0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ced0-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="9ced0-105">成员</span><span class="sxs-lookup"><span data-stu-id="9ced0-105">Members</span></span>  
  
|<span data-ttu-id="9ced0-106">成员</span><span class="sxs-lookup"><span data-stu-id="9ced0-106">Member</span></span>|<span data-ttu-id="9ced0-107">描述</span><span class="sxs-lookup"><span data-stu-id="9ced0-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="9ced0-108">指示默认未初始化模式。</span><span class="sxs-lookup"><span data-stu-id="9ced0-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="9ced0-109">指示用于卸载程序集的未初始化模式。</span><span class="sxs-lookup"><span data-stu-id="9ced0-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ced0-110">要求</span><span class="sxs-lookup"><span data-stu-id="9ced0-110">Requirements</span></span>  
 <span data-ttu-id="9ced0-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ced0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ced0-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ced0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ced0-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9ced0-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9ced0-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ced0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ced0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ced0-115">See also</span></span>

- [<span data-ttu-id="9ced0-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="9ced0-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
