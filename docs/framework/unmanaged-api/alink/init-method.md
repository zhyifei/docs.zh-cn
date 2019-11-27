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
ms.openlocfilehash: 986ae69e7ebb8f607be5d37fab426bcc787abb26
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445639"
---
# <a name="init-method"></a><span data-ttu-id="a65d2-102">Init 方法</span><span class="sxs-lookup"><span data-stu-id="a65d2-102">Init Method</span></span>
<span data-ttu-id="a65d2-103">准备实现[IALink 接口](ialink-interface.md)以便使用的对象。</span><span class="sxs-lookup"><span data-stu-id="a65d2-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="a65d2-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a65d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="a65d2-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="a65d2-106">指向元数据分配器的[IMetaDataDispenserEx 接口](../metadata/imetadatadispenserex-interface.md)指针。</span><span class="sxs-lookup"><span data-stu-id="a65d2-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="a65d2-107">指向可选错误处理接口的[IMetaDataError 接口](../metadata/imetadataerror-interface.md)指针。</span><span class="sxs-lookup"><span data-stu-id="a65d2-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a65d2-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a65d2-108">Return Value</span></span>  
 <span data-ttu-id="a65d2-109">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a65d2-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a65d2-110">要求</span><span class="sxs-lookup"><span data-stu-id="a65d2-110">Requirements</span></span>  
 <span data-ttu-id="a65d2-111">需要 alink</span><span class="sxs-lookup"><span data-stu-id="a65d2-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65d2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a65d2-112">See also</span></span>

- [<span data-ttu-id="a65d2-113">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="a65d2-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a65d2-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="a65d2-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a65d2-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="a65d2-115">ALink API</span></span>](index.md)
