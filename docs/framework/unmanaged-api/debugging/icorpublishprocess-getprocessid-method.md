---
title: ICorPublishProcess::GetProcessID 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790558"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="ea58a-102">ICorPublishProcess::GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="ea58a-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="ea58a-103">获取此进程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="ea58a-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea58a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea58a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea58a-105">参数</span><span class="sxs-lookup"><span data-stu-id="ea58a-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="ea58a-106">弄一个指针，指向此[ICorPublishProcess](icorpublishprocess-interface.md)对象所表示的进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="ea58a-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea58a-107">需求</span><span class="sxs-lookup"><span data-stu-id="ea58a-107">Requirements</span></span>  
 <span data-ttu-id="ea58a-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea58a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea58a-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="ea58a-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ea58a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea58a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea58a-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea58a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea58a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea58a-112">See also</span></span>

- [<span data-ttu-id="ea58a-113">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="ea58a-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
