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
ms.openlocfilehash: e8f9eecd6d6d74717eb7c1e389bfa24e40afc950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402569"
---
# <a name="endmerge-method"></a><span data-ttu-id="e4219-102">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="e4219-102">EndMerge Method</span></span>
<span data-ttu-id="e4219-103">指示所有自定义特性有已合并到发出范围。</span><span class="sxs-lookup"><span data-stu-id="e4219-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4219-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4219-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4219-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4219-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e4219-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="e4219-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4219-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e4219-107">Return Value</span></span>  
 <span data-ttu-id="e4219-108">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e4219-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4219-109">要求</span><span class="sxs-lookup"><span data-stu-id="e4219-109">Requirements</span></span>  
 <span data-ttu-id="e4219-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="e4219-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4219-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4219-111">See Also</span></span>  
 [<span data-ttu-id="e4219-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="e4219-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e4219-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="e4219-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e4219-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="e4219-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
