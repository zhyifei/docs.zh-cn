---
title: CloseEnum 方法
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5c3185dc6d488223d5882f543f0c690d82261b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402439"
---
# <a name="closeenum-method"></a><span data-ttu-id="b9ffd-102">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="b9ffd-102">CloseEnum Method</span></span>
<span data-ttu-id="b9ffd-103">关闭指定的枚举并释放关联的资源。</span><span class="sxs-lookup"><span data-stu-id="b9ffd-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ffd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9ffd-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ffd-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9ffd-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b9ffd-106">枚举即将关闭句柄。</span><span class="sxs-lookup"><span data-stu-id="b9ffd-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9ffd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b9ffd-107">Return Value</span></span>  
 <span data-ttu-id="b9ffd-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b9ffd-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ffd-109">要求</span><span class="sxs-lookup"><span data-stu-id="b9ffd-109">Requirements</span></span>  
 <span data-ttu-id="b9ffd-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="b9ffd-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ffd-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9ffd-111">See Also</span></span>  
 [<span data-ttu-id="b9ffd-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="b9ffd-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b9ffd-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="b9ffd-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b9ffd-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="b9ffd-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
