---
title: "COUNINITIEE 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COUNINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COUNINITIEE
helpviewer_keywords: COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c849a32850b5fc9aaca7ea75fdfb30db3de5d8c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="771da-102">COUNINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="771da-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="771da-103">指定使用的常量[CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)初始化公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="771da-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="771da-104">语法</span><span class="sxs-lookup"><span data-stu-id="771da-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="771da-105">成员</span><span class="sxs-lookup"><span data-stu-id="771da-105">Members</span></span>  
  
|<span data-ttu-id="771da-106">成员</span><span class="sxs-lookup"><span data-stu-id="771da-106">Member</span></span>|<span data-ttu-id="771da-107">描述</span><span class="sxs-lookup"><span data-stu-id="771da-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="771da-108">指示默认未初始化模式。</span><span class="sxs-lookup"><span data-stu-id="771da-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="771da-109">指示用于卸载程序集的未初始化模式。</span><span class="sxs-lookup"><span data-stu-id="771da-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="771da-110">要求</span><span class="sxs-lookup"><span data-stu-id="771da-110">Requirements</span></span>  
 <span data-ttu-id="771da-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="771da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="771da-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="771da-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="771da-113">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="771da-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="771da-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="771da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771da-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="771da-115">See Also</span></span>  
 [<span data-ttu-id="771da-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="771da-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
