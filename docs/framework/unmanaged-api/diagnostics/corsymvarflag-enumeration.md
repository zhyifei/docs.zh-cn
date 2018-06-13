---
title: CorSymVarFlag 枚举
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6a9c5ff91989fc1ad7da4e23df0e80d9d74ec7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424971"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="1287d-102">CorSymVarFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="1287d-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="1287d-103">指示变量是否由编译器生成。</span><span class="sxs-lookup"><span data-stu-id="1287d-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1287d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1287d-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="1287d-105">成员</span><span class="sxs-lookup"><span data-stu-id="1287d-105">Members</span></span>  
  
|<span data-ttu-id="1287d-106">成员</span><span class="sxs-lookup"><span data-stu-id="1287d-106">Member</span></span>|<span data-ttu-id="1287d-107">描述</span><span class="sxs-lookup"><span data-stu-id="1287d-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="1287d-108">指示给定的变量是编译器生成的。</span><span class="sxs-lookup"><span data-stu-id="1287d-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1287d-109">要求</span><span class="sxs-lookup"><span data-stu-id="1287d-109">Requirements</span></span>  
 <span data-ttu-id="1287d-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1287d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1287d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1287d-111">See Also</span></span>  
 [<span data-ttu-id="1287d-112">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="1287d-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
