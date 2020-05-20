---
title: INotifyConnection2::UnregisterNotifySource 方法
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442041"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="57339-102">INotifyConnection2::UnregisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="57339-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="57339-103">从连接中删除指定的通知源对象。</span><span class="sxs-lookup"><span data-stu-id="57339-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57339-104">语法</span><span class="sxs-lookup"><span data-stu-id="57339-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57339-105">参数</span><span class="sxs-lookup"><span data-stu-id="57339-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="57339-106">中要注销的通知对象。</span><span class="sxs-lookup"><span data-stu-id="57339-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57339-107">返回值</span><span class="sxs-lookup"><span data-stu-id="57339-107">Return Value</span></span>  
 <span data-ttu-id="57339-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="57339-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57339-109">要求</span><span class="sxs-lookup"><span data-stu-id="57339-109">Requirements</span></span>  
 <span data-ttu-id="57339-110">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="57339-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57339-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57339-111">See also</span></span>

- [<span data-ttu-id="57339-112">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="57339-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="57339-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="57339-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="57339-114">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="57339-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="57339-115">RegisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="57339-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
