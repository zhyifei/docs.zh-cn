---
title: EndMerge 方法
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88f594117fffedb6acafef26a9e834dd951ea5bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787529"
---
# <a name="endmerge-method"></a><span data-ttu-id="167e6-102">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="167e6-102">EndMerge Method</span></span>
<span data-ttu-id="167e6-103">指示所有自定义特性都已合并到发出范围中。</span><span class="sxs-lookup"><span data-stu-id="167e6-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="167e6-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="167e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="167e6-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="167e6-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="167e6-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="167e6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="167e6-107">Return Value</span></span>  
 <span data-ttu-id="167e6-108">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="167e6-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="167e6-109">要求</span><span class="sxs-lookup"><span data-stu-id="167e6-109">Requirements</span></span>  
 <span data-ttu-id="167e6-110">需要 alink</span><span class="sxs-lookup"><span data-stu-id="167e6-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="167e6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="167e6-111">See also</span></span>

- [<span data-ttu-id="167e6-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="167e6-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="167e6-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="167e6-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="167e6-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="167e6-114">ALink API</span></span>](index.md)
