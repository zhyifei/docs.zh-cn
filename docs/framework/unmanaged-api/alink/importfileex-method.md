---
title: ImportFileEx 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777113"
---
# <a name="importfileex-method"></a><span data-ttu-id="ef16b-102">ImportFileEx 方法</span><span class="sxs-lookup"><span data-stu-id="ef16b-102">ImportFileEx Method</span></span>
<span data-ttu-id="ef16b-103">导入指定的程序集或未绑定模块。</span><span class="sxs-lookup"><span data-stu-id="ef16b-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef16b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef16b-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef16b-105">参数</span><span class="sxs-lookup"><span data-stu-id="ef16b-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="ef16b-106">要导入的文件的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="ef16b-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="ef16b-107">目标文件的可选名称。</span><span class="sxs-lookup"><span data-stu-id="ef16b-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="ef16b-108">如果为 TRUE，则使用 ImportTypes，否则必须手动执行导入。</span><span class="sxs-lookup"><span data-stu-id="ef16b-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="ef16b-109">要传递给[OpenScope 方法](../metadata/imetadatadispenser-openscope-method.md)的标志。</span><span class="sxs-lookup"><span data-stu-id="ef16b-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="ef16b-110">接收正在导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="ef16b-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="ef16b-111">接收程序集导入范围[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ef16b-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="ef16b-112">如果文件不是程序集，则设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ef16b-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="ef16b-113">接收导入文件和/或范围的计数。</span><span class="sxs-lookup"><span data-stu-id="ef16b-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef16b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="ef16b-114">Return Value</span></span>  
 <span data-ttu-id="ef16b-115">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ef16b-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef16b-116">要求</span><span class="sxs-lookup"><span data-stu-id="ef16b-116">Requirements</span></span>  
 <span data-ttu-id="ef16b-117">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="ef16b-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef16b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef16b-118">See also</span></span>

- [<span data-ttu-id="ef16b-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="ef16b-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ef16b-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="ef16b-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ef16b-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="ef16b-121">ALink API</span></span>](index.md)
