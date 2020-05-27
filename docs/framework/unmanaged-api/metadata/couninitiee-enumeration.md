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
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008907"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="29f3a-102">COUNINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="29f3a-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="29f3a-103">指定初始化公共语言运行时[CoUninitializeEE](../hosting/couninitializeee-function.md)使用的常量。</span><span class="sxs-lookup"><span data-stu-id="29f3a-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="29f3a-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="29f3a-105">成员</span><span class="sxs-lookup"><span data-stu-id="29f3a-105">Members</span></span>  
  
|<span data-ttu-id="29f3a-106">成员</span><span class="sxs-lookup"><span data-stu-id="29f3a-106">Member</span></span>|<span data-ttu-id="29f3a-107">描述</span><span class="sxs-lookup"><span data-stu-id="29f3a-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="29f3a-108">指示默认取消初始化模式。</span><span class="sxs-lookup"><span data-stu-id="29f3a-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="29f3a-109">指示用于卸载程序集的取消初始化模式。</span><span class="sxs-lookup"><span data-stu-id="29f3a-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29f3a-110">要求</span><span class="sxs-lookup"><span data-stu-id="29f3a-110">Requirements</span></span>  
 <span data-ttu-id="29f3a-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29f3a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f3a-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="29f3a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29f3a-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="29f3a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29f3a-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29f3a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f3a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29f3a-115">See also</span></span>

- [<span data-ttu-id="29f3a-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="29f3a-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
