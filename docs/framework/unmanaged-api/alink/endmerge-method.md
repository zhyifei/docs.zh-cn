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
ms.openlocfilehash: 8daf76e50b4c584115a55936aa9336c95a3669ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742077"
---
# <a name="endmerge-method"></a><span data-ttu-id="ec185-102">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="ec185-102">EndMerge Method</span></span>
<span data-ttu-id="ec185-103">指示到发出范围合并所有自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ec185-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec185-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec185-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec185-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec185-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ec185-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="ec185-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec185-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ec185-107">Return Value</span></span>  
 <span data-ttu-id="ec185-108">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ec185-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec185-109">要求</span><span class="sxs-lookup"><span data-stu-id="ec185-109">Requirements</span></span>  
 <span data-ttu-id="ec185-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="ec185-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec185-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec185-111">See also</span></span>

- [<span data-ttu-id="ec185-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="ec185-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ec185-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="ec185-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ec185-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="ec185-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
