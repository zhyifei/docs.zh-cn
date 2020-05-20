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
ms.openlocfilehash: d41e048b67d4bc7159f6dd5266457651f1658290
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420586"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="7cff7-102">CorSymVarFlag 枚举</span><span class="sxs-lookup"><span data-stu-id="7cff7-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="7cff7-103">指示变量是否是编译器生成的。</span><span class="sxs-lookup"><span data-stu-id="7cff7-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cff7-104">语法</span><span class="sxs-lookup"><span data-stu-id="7cff7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="7cff7-105">成员</span><span class="sxs-lookup"><span data-stu-id="7cff7-105">Members</span></span>  
  
|<span data-ttu-id="7cff7-106">成员</span><span class="sxs-lookup"><span data-stu-id="7cff7-106">Member</span></span>|<span data-ttu-id="7cff7-107">描述</span><span class="sxs-lookup"><span data-stu-id="7cff7-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="7cff7-108">指示给定变量是编译器生成的。</span><span class="sxs-lookup"><span data-stu-id="7cff7-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7cff7-109">要求</span><span class="sxs-lookup"><span data-stu-id="7cff7-109">Requirements</span></span>  
 <span data-ttu-id="7cff7-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="7cff7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cff7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cff7-111">See also</span></span>

- [<span data-ttu-id="7cff7-112">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="7cff7-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
