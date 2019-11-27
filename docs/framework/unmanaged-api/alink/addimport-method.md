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
ms.openlocfilehash: 52e52ac62e2dcfeb182da3014a863409f640274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446656"
---
# <a name="addimport-method"></a><span data-ttu-id="41915-102">AddImport 方法</span><span class="sxs-lookup"><span data-stu-id="41915-102">AddImport Method</span></span>
<span data-ttu-id="41915-103">将导入添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="41915-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41915-104">语法</span><span class="sxs-lookup"><span data-stu-id="41915-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="41915-105">参数</span><span class="sxs-lookup"><span data-stu-id="41915-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="41915-106">要扩充的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="41915-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="41915-107">要导入的文件从[ImportFile 方法](importfile-method.md)检索的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="41915-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="41915-108">COM + FileDef 标志，如 `ffContainsNoMetaData` 和 `ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="41915-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="41915-109">`dwFlags` 传递给[DefineFile 方法](../metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="41915-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="41915-110">指向接收结果文件的 ID 的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="41915-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41915-111">返回值</span><span class="sxs-lookup"><span data-stu-id="41915-111">Return Value</span></span>  
 <span data-ttu-id="41915-112">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="41915-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41915-113">要求</span><span class="sxs-lookup"><span data-stu-id="41915-113">Requirements</span></span>  
 <span data-ttu-id="41915-114">需要 alink</span><span class="sxs-lookup"><span data-stu-id="41915-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41915-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41915-115">See also</span></span>

- [<span data-ttu-id="41915-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="41915-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="41915-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="41915-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="41915-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="41915-118">ALink API</span></span>](index.md)
