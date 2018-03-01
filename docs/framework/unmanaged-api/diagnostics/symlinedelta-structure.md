---
title: "SYMLINEDELTA 结构"
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
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 677b7c2858e4f3248e0d46e460b9eef09de724f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="48c98-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="48c98-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="48c98-103">提供有关方法的结果编辑已移动到符号处理程序信息。</span><span class="sxs-lookup"><span data-stu-id="48c98-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c98-104">语法</span><span class="sxs-lookup"><span data-stu-id="48c98-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="48c98-105">成员</span><span class="sxs-lookup"><span data-stu-id="48c98-105">Members</span></span>  
  
|<span data-ttu-id="48c98-106">成员</span><span class="sxs-lookup"><span data-stu-id="48c98-106">Member</span></span>|<span data-ttu-id="48c98-107">描述</span><span class="sxs-lookup"><span data-stu-id="48c98-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="48c98-108">方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="48c98-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="48c98-109">该方法已移动的行数。</span><span class="sxs-lookup"><span data-stu-id="48c98-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48c98-110">惠?</span><span class="sxs-lookup"><span data-stu-id="48c98-110">Requirements</span></span>  
 <span data-ttu-id="48c98-111">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="48c98-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c98-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="48c98-112">See Also</span></span>  
 [<span data-ttu-id="48c98-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="48c98-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
