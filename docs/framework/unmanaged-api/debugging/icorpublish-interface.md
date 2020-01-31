---
title: ICorPublish 接口
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790726"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="0dc60-102">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="0dc60-102">ICorPublish Interface</span></span>
<span data-ttu-id="0dc60-103">用作发布有关进程的信息，以及有关这些进程中的应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="0dc60-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0dc60-104">方法</span><span class="sxs-lookup"><span data-stu-id="0dc60-104">Methods</span></span>  
  
|<span data-ttu-id="0dc60-105">方法</span><span class="sxs-lookup"><span data-stu-id="0dc60-105">Method</span></span>|<span data-ttu-id="0dc60-106">描述</span><span class="sxs-lookup"><span data-stu-id="0dc60-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0dc60-107">EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="0dc60-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="0dc60-108">获取一个[ICorPublishProcessEnum](icorpublishprocessenum-interface.md)实例，它包含在此计算机上运行的托管进程。</span><span class="sxs-lookup"><span data-stu-id="0dc60-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="0dc60-109">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="0dc60-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="0dc60-110">获取一个表示具有指定标识符的进程的[ICorPublishProcess](icorpublishprocess-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="0dc60-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dc60-111">需求</span><span class="sxs-lookup"><span data-stu-id="0dc60-111">Requirements</span></span>  
 <span data-ttu-id="0dc60-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc60-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dc60-113">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="0dc60-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0dc60-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dc60-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dc60-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc60-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc60-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dc60-116">See also</span></span>

- [<span data-ttu-id="0dc60-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="0dc60-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0dc60-118">CorpubPublish 组件类</span><span class="sxs-lookup"><span data-stu-id="0dc60-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
