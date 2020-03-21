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
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176118"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="26617-102">COUNINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="26617-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="26617-103">指定[CoUn初始化 EE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)在初始化通用语言运行时使用的常量。</span><span class="sxs-lookup"><span data-stu-id="26617-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26617-104">语法</span><span class="sxs-lookup"><span data-stu-id="26617-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="26617-105">成员</span><span class="sxs-lookup"><span data-stu-id="26617-105">Members</span></span>  
  
|<span data-ttu-id="26617-106">成员</span><span class="sxs-lookup"><span data-stu-id="26617-106">Member</span></span>|<span data-ttu-id="26617-107">说明</span><span class="sxs-lookup"><span data-stu-id="26617-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="26617-108">指示默认的未初始化模式。</span><span class="sxs-lookup"><span data-stu-id="26617-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="26617-109">指示卸载程序集的未初始化模式。</span><span class="sxs-lookup"><span data-stu-id="26617-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26617-110">要求</span><span class="sxs-lookup"><span data-stu-id="26617-110">Requirements</span></span>  
 <span data-ttu-id="26617-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26617-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26617-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="26617-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26617-113">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="26617-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26617-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26617-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26617-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26617-115">See also</span></span>

- [<span data-ttu-id="26617-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="26617-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
