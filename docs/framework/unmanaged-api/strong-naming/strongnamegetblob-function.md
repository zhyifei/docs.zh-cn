---
title: StrongNameGetBlob 函数
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d5b3d1d39b5d4c5b7d4db073b3ffaf1c6b88373
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799097"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="128ff-102">StrongNameGetBlob 函数</span><span class="sxs-lookup"><span data-stu-id="128ff-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="128ff-103">使用指定地址处可执行文件的二进制表示形式填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="128ff-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="128ff-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="128ff-104">This function has been deprecated.</span></span> <span data-ttu-id="128ff-105">改为使用[ICLRStrongName：： StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="128ff-105">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="128ff-106">语法</span><span class="sxs-lookup"><span data-stu-id="128ff-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="128ff-107">参数</span><span class="sxs-lookup"><span data-stu-id="128ff-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="128ff-108">中要加载的可执行文件的有效路径。</span><span class="sxs-lookup"><span data-stu-id="128ff-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="128ff-109">中要在其中加载可执行文件的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="128ff-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="128ff-110">[in，out]请求的最大大小（以字节为`pbBlob`单位）。</span><span class="sxs-lookup"><span data-stu-id="128ff-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="128ff-111">返回时，的实际大小（以字节为单位`pbBlob`）。</span><span class="sxs-lookup"><span data-stu-id="128ff-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="128ff-112">返回值</span><span class="sxs-lookup"><span data-stu-id="128ff-112">Return Value</span></span>  
 <span data-ttu-id="128ff-113">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="128ff-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="128ff-114">备注</span><span class="sxs-lookup"><span data-stu-id="128ff-114">Remarks</span></span>  
 <span data-ttu-id="128ff-115">如果`StrongNameGetBlob`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="128ff-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="128ff-116">要求</span><span class="sxs-lookup"><span data-stu-id="128ff-116">Requirements</span></span>  
 <span data-ttu-id="128ff-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="128ff-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="128ff-118">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="128ff-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="128ff-119">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="128ff-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="128ff-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="128ff-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="128ff-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="128ff-121">See also</span></span>

- [<span data-ttu-id="128ff-122">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="128ff-122">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="128ff-123">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="128ff-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="128ff-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="128ff-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
