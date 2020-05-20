---
title: INotifyConnection2::RegisterNotifySource 方法
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442067"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="81c2c-102">INotifyConnection2::RegisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="81c2c-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="81c2c-103">安装指定的通知源。</span><span class="sxs-lookup"><span data-stu-id="81c2c-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c2c-104">语法</span><span class="sxs-lookup"><span data-stu-id="81c2c-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81c2c-105">参数</span><span class="sxs-lookup"><span data-stu-id="81c2c-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="81c2c-106">中指定要用作通知源的对象。</span><span class="sxs-lookup"><span data-stu-id="81c2c-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="81c2c-107">弄接收要用作通知接收器的对象。</span><span class="sxs-lookup"><span data-stu-id="81c2c-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81c2c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="81c2c-108">Return Value</span></span>  
 <span data-ttu-id="81c2c-109">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="81c2c-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81c2c-110">要求</span><span class="sxs-lookup"><span data-stu-id="81c2c-110">Requirements</span></span>  
 <span data-ttu-id="81c2c-111">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="81c2c-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c2c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81c2c-112">See also</span></span>

- [<span data-ttu-id="81c2c-113">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="81c2c-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="81c2c-114">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="81c2c-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="81c2c-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="81c2c-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="81c2c-116">UnregisterNotifySource 方法</span><span class="sxs-lookup"><span data-stu-id="81c2c-116">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)
