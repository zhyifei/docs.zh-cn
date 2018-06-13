---
title: GetFileDef 方法
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b772ae37baed44b90e4f5420e0f7724201a56abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401806"
---
# <a name="getfiledef-method"></a><span data-ttu-id="63fbd-102">GetFileDef 方法</span><span class="sxs-lookup"><span data-stu-id="63fbd-102">GetFileDef Method</span></span>
<span data-ttu-id="63fbd-103">检索元数据 （而不是由 ALink 分配的令牌） 中使用的实际 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="63fbd-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63fbd-104">语法</span><span class="sxs-lookup"><span data-stu-id="63fbd-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63fbd-105">参数</span><span class="sxs-lookup"><span data-stu-id="63fbd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="63fbd-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="63fbd-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="63fbd-107">添加的文件的令牌从 AddFile 方法或 AddImport 方法中检索。</span><span class="sxs-lookup"><span data-stu-id="63fbd-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="63fbd-108">收到 FileDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="63fbd-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63fbd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="63fbd-109">Return Value</span></span>  
 <span data-ttu-id="63fbd-110">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="63fbd-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63fbd-111">要求</span><span class="sxs-lookup"><span data-stu-id="63fbd-111">Requirements</span></span>  
 <span data-ttu-id="63fbd-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="63fbd-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fbd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="63fbd-113">See Also</span></span>  
 [<span data-ttu-id="63fbd-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="63fbd-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="63fbd-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="63fbd-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="63fbd-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="63fbd-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
