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
ms.openlocfilehash: 9b6c839cc664105149f26b0d21d7ba7fb91b3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742198"
---
# <a name="closeenum-method"></a><span data-ttu-id="1661d-102">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="1661d-102">CloseEnum Method</span></span>
<span data-ttu-id="1661d-103">关闭指定的枚举，并释放关联的资源。</span><span class="sxs-lookup"><span data-stu-id="1661d-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1661d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1661d-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1661d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1661d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="1661d-106">枚举要关闭的句柄。</span><span class="sxs-lookup"><span data-stu-id="1661d-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1661d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1661d-107">Return Value</span></span>  
 <span data-ttu-id="1661d-108">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1661d-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1661d-109">要求</span><span class="sxs-lookup"><span data-stu-id="1661d-109">Requirements</span></span>  
 <span data-ttu-id="1661d-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="1661d-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1661d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1661d-111">See also</span></span>

- [<span data-ttu-id="1661d-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="1661d-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1661d-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="1661d-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1661d-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="1661d-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
