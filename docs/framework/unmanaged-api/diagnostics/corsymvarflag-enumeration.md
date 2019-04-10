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
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198850"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="b83c7-102">CorSymVarFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="b83c7-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="b83c7-103">指示变量是否由编译器生成。</span><span class="sxs-lookup"><span data-stu-id="b83c7-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b83c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="b83c7-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="b83c7-105">成员</span><span class="sxs-lookup"><span data-stu-id="b83c7-105">Members</span></span>  
  
|<span data-ttu-id="b83c7-106">成员</span><span class="sxs-lookup"><span data-stu-id="b83c7-106">Member</span></span>|<span data-ttu-id="b83c7-107">描述</span><span class="sxs-lookup"><span data-stu-id="b83c7-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="b83c7-108">指示给定的变量是编译器生成。</span><span class="sxs-lookup"><span data-stu-id="b83c7-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b83c7-109">要求</span><span class="sxs-lookup"><span data-stu-id="b83c7-109">Requirements</span></span>  
 <span data-ttu-id="b83c7-110">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b83c7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83c7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b83c7-111">See also</span></span>

- [<span data-ttu-id="b83c7-112">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="b83c7-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
