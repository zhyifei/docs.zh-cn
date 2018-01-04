---
title: "CorSymVarFlag 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymVarFlag
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymVarFlag
helpviewer_keywords: CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b548a66f471eb3641da7407ed14d107c6b4fec8c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="c6a06-102">CorSymVarFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="c6a06-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="c6a06-103">指示变量是否由编译器生成。</span><span class="sxs-lookup"><span data-stu-id="c6a06-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6a06-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6a06-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="c6a06-105">成员</span><span class="sxs-lookup"><span data-stu-id="c6a06-105">Members</span></span>  
  
|<span data-ttu-id="c6a06-106">成员</span><span class="sxs-lookup"><span data-stu-id="c6a06-106">Member</span></span>|<span data-ttu-id="c6a06-107">描述</span><span class="sxs-lookup"><span data-stu-id="c6a06-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="c6a06-108">指示给定的变量是编译器生成的。</span><span class="sxs-lookup"><span data-stu-id="c6a06-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6a06-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c6a06-109">Requirements</span></span>  
 <span data-ttu-id="c6a06-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6a06-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a06-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a06-111">See Also</span></span>  
 [<span data-ttu-id="c6a06-112">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="c6a06-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
