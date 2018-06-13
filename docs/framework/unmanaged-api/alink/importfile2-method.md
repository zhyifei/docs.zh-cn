---
title: ImportFile2 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61bc7783823408164ae2b073e097a0e85e193be6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401237"
---
# <a name="importfile2-method"></a><span data-ttu-id="f2c3e-102">ImportFile2 方法</span><span class="sxs-lookup"><span data-stu-id="f2c3e-102">ImportFile2 Method</span></span>
<span data-ttu-id="f2c3e-103">导入程序集和未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="f2c3e-104">此方法就像是[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)，但是如果即使正在导入的文件不存在磁盘上的工作。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2c3e-105">语法</span><span class="sxs-lookup"><span data-stu-id="f2c3e-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2c3e-106">参数</span><span class="sxs-lookup"><span data-stu-id="f2c3e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f2c3e-107">要导入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="f2c3e-108">可用于重命名该文件并将其链接到程序集的可选的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="f2c3e-109">可选的作用域[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="f2c3e-110">如果为 TRUE，则使用 ImportTypes，必须手动执行否则导入。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="f2c3e-111">接收的文件或程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="f2c3e-112">接收[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="f2c3e-113">如果文件不是程序集为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="f2c3e-114">接收找到的文件和/或导入的作用域。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2c3e-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f2c3e-115">Return Value</span></span>  
 <span data-ttu-id="f2c3e-116">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2c3e-117">要求</span><span class="sxs-lookup"><span data-stu-id="f2c3e-117">Requirements</span></span>  
 <span data-ttu-id="f2c3e-118">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="f2c3e-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c3e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2c3e-119">See Also</span></span>  
 [<span data-ttu-id="f2c3e-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f2c3e-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f2c3e-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f2c3e-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f2c3e-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="f2c3e-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
