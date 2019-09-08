---
title: Init 方法
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787244"
---
# <a name="init-method"></a><span data-ttu-id="04a3a-102">Init 方法</span><span class="sxs-lookup"><span data-stu-id="04a3a-102">Init Method</span></span>
<span data-ttu-id="04a3a-103">准备实现[IALink 接口](ialink-interface.md)以便使用的对象。</span><span class="sxs-lookup"><span data-stu-id="04a3a-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04a3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="04a3a-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="04a3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="04a3a-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="04a3a-106">指向元数据分配器的[IMetaDataDispenserEx 接口](../metadata/imetadatadispenserex-interface.md)指针。</span><span class="sxs-lookup"><span data-stu-id="04a3a-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="04a3a-107">指向可选错误处理接口的[IMetaDataError 接口](../metadata/imetadataerror-interface.md)指针。</span><span class="sxs-lookup"><span data-stu-id="04a3a-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04a3a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="04a3a-108">Return Value</span></span>  
 <span data-ttu-id="04a3a-109">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="04a3a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04a3a-110">要求</span><span class="sxs-lookup"><span data-stu-id="04a3a-110">Requirements</span></span>  
 <span data-ttu-id="04a3a-111">需要 alink</span><span class="sxs-lookup"><span data-stu-id="04a3a-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a3a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="04a3a-112">See also</span></span>

- [<span data-ttu-id="04a3a-113">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="04a3a-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="04a3a-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="04a3a-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="04a3a-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="04a3a-115">ALink API</span></span>](index.md)
