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
ms.openlocfilehash: 018af6929ad4023c70bfb975b9be010912415dd7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446561"
---
# <a name="closeenum-method"></a><span data-ttu-id="e2ad4-102">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="e2ad4-102">CloseEnum Method</span></span>
<span data-ttu-id="e2ad4-103">关闭所指示的枚举并释放关联的资源。</span><span class="sxs-lookup"><span data-stu-id="e2ad4-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ad4-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2ad4-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2ad4-105">参数</span><span class="sxs-lookup"><span data-stu-id="e2ad4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e2ad4-106">要关闭的枚举的句柄。</span><span class="sxs-lookup"><span data-stu-id="e2ad4-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2ad4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e2ad4-107">Return Value</span></span>  
 <span data-ttu-id="e2ad4-108">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e2ad4-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ad4-109">要求</span><span class="sxs-lookup"><span data-stu-id="e2ad4-109">Requirements</span></span>  
 <span data-ttu-id="e2ad4-110">需要 alink</span><span class="sxs-lookup"><span data-stu-id="e2ad4-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ad4-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2ad4-111">See also</span></span>

- [<span data-ttu-id="e2ad4-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="e2ad4-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e2ad4-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="e2ad4-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e2ad4-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="e2ad4-114">ALink API</span></span>](index.md)
