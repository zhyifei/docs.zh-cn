---
title: ImportFileEx2 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1c950e9a6e53e04cc0f2e52a140612562b32ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776980"
---
# <a name="importfileex2-method"></a><span data-ttu-id="a503e-102">ImportFileEx2 方法</span><span class="sxs-lookup"><span data-stu-id="a503e-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="a503e-103">导入程序集和未绑定模块。</span><span class="sxs-lookup"><span data-stu-id="a503e-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="a503e-104">此方法类似于[ImportFile 方法](importfile-method.md)，但即使磁盘上没有要导入的文件也能正常工作。</span><span class="sxs-lookup"><span data-stu-id="a503e-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a503e-105">语法</span><span class="sxs-lookup"><span data-stu-id="a503e-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a503e-106">参数</span><span class="sxs-lookup"><span data-stu-id="a503e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="a503e-107">要导入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a503e-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="a503e-108">目标文件的可选名称。</span><span class="sxs-lookup"><span data-stu-id="a503e-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="a503e-109">可选的导入范围[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a503e-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="a503e-110">如果为 TRUE，则使用 ImportTypes，否则必须手动执行导入。</span><span class="sxs-lookup"><span data-stu-id="a503e-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a503e-111">要传递给[OpenScope 方法](../metadata/imetadatadispenser-openscope-method.md)的标志。</span><span class="sxs-lookup"><span data-stu-id="a503e-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="a503e-112">接收程序集或文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a503e-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="a503e-113">接收程序集导入范围[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a503e-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="a503e-114">如果文件不是程序集，则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a503e-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="a503e-115">接收导入的文件和/或范围的数量。</span><span class="sxs-lookup"><span data-stu-id="a503e-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a503e-116">返回值</span><span class="sxs-lookup"><span data-stu-id="a503e-116">Return Value</span></span>  
 <span data-ttu-id="a503e-117">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a503e-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a503e-118">要求</span><span class="sxs-lookup"><span data-stu-id="a503e-118">Requirements</span></span>  
 <span data-ttu-id="a503e-119">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="a503e-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a503e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a503e-120">See also</span></span>

- [<span data-ttu-id="a503e-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="a503e-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a503e-122">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="a503e-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a503e-123">ALink API</span><span class="sxs-lookup"><span data-stu-id="a503e-123">ALink API</span></span>](index.md)
