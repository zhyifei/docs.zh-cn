---
title: "COINITIEE 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="20785-102">COINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="20785-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="20785-103">指定使用的常量[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)初始化公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="20785-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20785-104">语法</span><span class="sxs-lookup"><span data-stu-id="20785-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="20785-105">成员</span><span class="sxs-lookup"><span data-stu-id="20785-105">Members</span></span>  
  
|<span data-ttu-id="20785-106">成员</span><span class="sxs-lookup"><span data-stu-id="20785-106">Member</span></span>|<span data-ttu-id="20785-107">描述</span><span class="sxs-lookup"><span data-stu-id="20785-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="20785-108">默认值初始化模式。</span><span class="sxs-lookup"><span data-stu-id="20785-108">Default initialization mode.</span></span> <span data-ttu-id="20785-109">此初始化运行时并创建默认<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="20785-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="20785-110">初始化运行了托管的 DLL。</span><span class="sxs-lookup"><span data-stu-id="20785-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="20785-111">初始化运行托管可执行程序。</span><span class="sxs-lookup"><span data-stu-id="20785-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="20785-112">此初始化运行时，但不会创建默认值<xref:System.AppDomain>，它在输入该 exe 文件的 main 例程后在创建。</span><span class="sxs-lookup"><span data-stu-id="20785-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20785-113">惠?</span><span class="sxs-lookup"><span data-stu-id="20785-113">Requirements</span></span>  
 <span data-ttu-id="20785-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20785-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20785-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="20785-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20785-116">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="20785-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20785-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20785-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20785-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="20785-118">See Also</span></span>  
 [<span data-ttu-id="20785-119">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="20785-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
