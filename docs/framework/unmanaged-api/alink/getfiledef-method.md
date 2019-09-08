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
ms.openlocfilehash: 5db205993bc1a0665dc0003948ce805813251f48
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787451"
---
# <a name="getfiledef-method"></a><span data-ttu-id="4d026-102">GetFileDef 方法</span><span class="sxs-lookup"><span data-stu-id="4d026-102">GetFileDef Method</span></span>
<span data-ttu-id="4d026-103">检索在元数据中使用的实际 FileDef 令牌（而不是由 ALink 分配的令牌）。</span><span class="sxs-lookup"><span data-stu-id="4d026-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d026-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d026-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d026-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d026-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4d026-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="4d026-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="4d026-107">从 AddFile 方法或 AddImport 方法检索到的已添加文件的标记。</span><span class="sxs-lookup"><span data-stu-id="4d026-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="4d026-108">接收 FileDef 标记。</span><span class="sxs-lookup"><span data-stu-id="4d026-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d026-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4d026-109">Return Value</span></span>  
 <span data-ttu-id="4d026-110">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4d026-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d026-111">要求</span><span class="sxs-lookup"><span data-stu-id="4d026-111">Requirements</span></span>  
 <span data-ttu-id="4d026-112">需要 alink</span><span class="sxs-lookup"><span data-stu-id="4d026-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d026-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d026-113">See also</span></span>

- [<span data-ttu-id="4d026-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="4d026-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4d026-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="4d026-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4d026-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="4d026-116">ALink API</span></span>](index.md)
