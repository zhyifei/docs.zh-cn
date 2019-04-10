---
title: AddImport 方法
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bbe8a43f44d59249abc713c95fce31f1fb9a5993
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148663"
---
# <a name="addimport-method"></a><span data-ttu-id="4fd20-102">AddImport 方法</span><span class="sxs-lookup"><span data-stu-id="4fd20-102">AddImport Method</span></span>
<span data-ttu-id="4fd20-103">将导入添加到该程序集。</span><span class="sxs-lookup"><span data-stu-id="4fd20-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd20-104">语法</span><span class="sxs-lookup"><span data-stu-id="4fd20-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fd20-105">参数</span><span class="sxs-lookup"><span data-stu-id="4fd20-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4fd20-106">要进行扩充程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="4fd20-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="4fd20-107">从检索唯一 ID [ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)，要导入文件。</span><span class="sxs-lookup"><span data-stu-id="4fd20-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4fd20-108">COM + FileDef 标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="4fd20-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> `dwFlags` <span data-ttu-id="4fd20-109">传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd20-109">is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="4fd20-110">指向接收生成的文件的 ID 的标记。</span><span class="sxs-lookup"><span data-stu-id="4fd20-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fd20-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4fd20-111">Return Value</span></span>  
 <span data-ttu-id="4fd20-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4fd20-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fd20-113">要求</span><span class="sxs-lookup"><span data-stu-id="4fd20-113">Requirements</span></span>  
 <span data-ttu-id="4fd20-114">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="4fd20-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd20-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fd20-115">See also</span></span>

- [<span data-ttu-id="4fd20-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="4fd20-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4fd20-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="4fd20-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4fd20-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="4fd20-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
