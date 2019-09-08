---
title: SetNonAssemblyFlags 方法
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8a22e958740b69ba0e09bf062bf4d86075c3ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777021"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="b28c9-102">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="b28c9-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="b28c9-103">设置不是程序集特定的标志。</span><span class="sxs-lookup"><span data-stu-id="b28c9-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="b28c9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="b28c9-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="b28c9-106">ALink 标志。</span><span class="sxs-lookup"><span data-stu-id="b28c9-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28c9-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b28c9-107">Return Value</span></span>  
 <span data-ttu-id="b28c9-108">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b28c9-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28c9-109">要求</span><span class="sxs-lookup"><span data-stu-id="b28c9-109">Requirements</span></span>  
 <span data-ttu-id="b28c9-110">需要 alink</span><span class="sxs-lookup"><span data-stu-id="b28c9-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28c9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b28c9-111">See also</span></span>

- [<span data-ttu-id="b28c9-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="b28c9-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b28c9-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="b28c9-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b28c9-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="b28c9-114">ALink API</span></span>](index.md)
