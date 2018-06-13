---
title: AddFile Method1
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57a350fadfa77fdad545ca7ccf2f63d28607c2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403915"
---
# <a name="addfile-method1"></a><span data-ttu-id="9abd3-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="9abd3-102">AddFile Method1</span></span>
<span data-ttu-id="9abd3-103">将文件添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="9abd3-103">Adds files to the assembly.</span></span> <span data-ttu-id="9abd3-104">此外可以用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="9abd3-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9abd3-105">语法</span><span class="sxs-lookup"><span data-stu-id="9abd3-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9abd3-106">参数</span><span class="sxs-lookup"><span data-stu-id="9abd3-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9abd3-107">要进行扩充的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9abd3-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="9abd3-108">要添加的文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="9abd3-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9abd3-109">COM + FileDef 标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="9abd3-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="9abd3-110">`dwFlags` 传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="9abd3-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="9abd3-111">[IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口用于发出元数据，如有必要。</span><span class="sxs-lookup"><span data-stu-id="9abd3-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="9abd3-112">指向将存储添加的文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9abd3-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9abd3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="9abd3-113">Return Value</span></span>  
 <span data-ttu-id="9abd3-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="9abd3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9abd3-115">要求</span><span class="sxs-lookup"><span data-stu-id="9abd3-115">Requirements</span></span>  
 <span data-ttu-id="9abd3-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="9abd3-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9abd3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9abd3-117">See Also</span></span>  
 [<span data-ttu-id="9abd3-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="9abd3-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9abd3-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="9abd3-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9abd3-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="9abd3-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
