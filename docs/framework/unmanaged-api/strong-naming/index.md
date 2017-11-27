---
title: "强命名（非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86d741a16a0293892d0d6d90f1763d744ed3675d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="c1345-102">强命名（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c1345-102">Strong Naming (Unmanaged API Reference)</span></span>
<span data-ttu-id="c1345-103">强命名 API 允许客户端管理的程序集强名称签名。</span><span class="sxs-lookup"><span data-stu-id="c1345-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="c1345-104">使用强名称对程序集进行签名将向包含程序集清单的文件添加公钥加密。</span><span class="sxs-lookup"><span data-stu-id="c1345-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="c1345-105">强名称签名帮助验证名称的唯一性，避免名称欺骗，并解析引用时将调用方提供的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="c1345-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="c1345-106">但是，没有的信任级别都具有强名称相关联。</span><span class="sxs-lookup"><span data-stu-id="c1345-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1345-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="c1345-107">In This Section</span></span>  
 [<span data-ttu-id="c1345-108">强命名的全局静态函数</span><span class="sxs-lookup"><span data-stu-id="c1345-108">Strong Naming Global Static Functions</span></span>](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 <span data-ttu-id="c1345-109">描述强命名 API 使用的非托管全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="c1345-109">Describes the unmanaged global static functions that the strong naming API uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1345-110">所有这些函数已弃用开头[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-110">All of these functions have been deprecated starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c1345-111">建议的替代，请参阅[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c1345-111">For suggested alternatives, see the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="c1345-112">GetHashFromAssemblyFile 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-112">GetHashFromAssemblyFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 <span data-ttu-id="c1345-113">获取使用指定的哈希算法对指定的程序集文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="c1345-113">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="c1345-114">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-114">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-115">GetHashFromAssemblyFileW 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-115">GetHashFromAssemblyFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="c1345-116">获取为 Unicode 字符串，使用指定的哈希算法指定的程序集文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="c1345-116">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="c1345-117">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-117">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-118">GetHashFromBlob 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-118">GetHashFromBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 <span data-ttu-id="c1345-119">获取指定的内存地址，使用指定的哈希算法的程序集哈希值。</span><span class="sxs-lookup"><span data-stu-id="c1345-119">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="c1345-120">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-120">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-121">GetHashFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-121">GetHashFromFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 <span data-ttu-id="c1345-122">生成指定的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="c1345-122">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="c1345-123">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-123">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-124">GetHashFromFileW 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-124">GetHashFromFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 <span data-ttu-id="c1345-125">生成指定的 Unicode 字符串的文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="c1345-125">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="c1345-126">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-126">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-127">GetHashFromHandle 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-127">GetHashFromHandle Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 <span data-ttu-id="c1345-128">生成与指定的文件句柄，使用指定的哈希算法文件的内容哈希代码。</span><span class="sxs-lookup"><span data-stu-id="c1345-128">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="c1345-129">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-129">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-130">StrongNameCompareAssemblies 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-130">StrongNameCompareAssemblies Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 <span data-ttu-id="c1345-131">确定是否两个程序集的差异仅在于其强名称签名。</span><span class="sxs-lookup"><span data-stu-id="c1345-131">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="c1345-132">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-132">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-133">StrongNameErrorInfo 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-133">StrongNameErrorInfo Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 <span data-ttu-id="c1345-134">获取引发的强名称函数之一的最后一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="c1345-134">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="c1345-135">StrongNameFreeBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-135">StrongNameFreeBuffer Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 <span data-ttu-id="c1345-136">释放通过以前对强名称函数调用如分配的内存[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)， [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)，或[StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="c1345-136">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="c1345-137">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-137">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-138">StrongNameGetBlob 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-138">StrongNameGetBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 <span data-ttu-id="c1345-139">用的二进制表示形式指定地址处的可执行文件填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c1345-139">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="c1345-140">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-140">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-141">StrongNameGetBlobFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-141">StrongNameGetBlobFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="c1345-142">获取位于指定的内存地址处的二进制表示形式的程序集映像。</span><span class="sxs-lookup"><span data-stu-id="c1345-142">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="c1345-143">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-143">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-144">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-144">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 <span data-ttu-id="c1345-145">获取从私钥/公钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="c1345-145">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="c1345-146">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-146">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-147">StrongNameHashSize 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-147">StrongNameHashSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 <span data-ttu-id="c1345-148">获取使用指定的哈希算法的哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="c1345-148">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="c1345-149">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-149">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-150">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-150">StrongNameKeyDelete Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 <span data-ttu-id="c1345-151">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="c1345-151">Deletes the specified key container.</span></span> <span data-ttu-id="c1345-152">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-152">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-153">StrongNameKeyGen 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-153">StrongNameKeyGen Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 <span data-ttu-id="c1345-154">创建强名称使用新的公钥/私钥密钥对。</span><span class="sxs-lookup"><span data-stu-id="c1345-154">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="c1345-155">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-155">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-156">StrongNameKeyGenEx 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-156">StrongNameKeyGenEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 <span data-ttu-id="c1345-157">生成具有强名称用于指定的密钥大小的新公钥/私钥密钥对。</span><span class="sxs-lookup"><span data-stu-id="c1345-157">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="c1345-158">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-158">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-159">StrongNameKeyInstall 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-159">StrongNameKeyInstall Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 <span data-ttu-id="c1345-160">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="c1345-160">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="c1345-161">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-161">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-162">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-162">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="c1345-163">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="c1345-163">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="c1345-164">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-164">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-165">StrongNameSignatureGenerationEx 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-165">StrongNameSignatureGenerationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="c1345-166">基于指定的标志指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="c1345-166">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="c1345-167">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-167">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-168">StrongNameSignatureSize 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-168">StrongNameSignatureSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 <span data-ttu-id="c1345-169">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="c1345-169">Returns the size of the strong name signature.</span></span> <span data-ttu-id="c1345-170">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-170">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-171">StrongNameSignatureVerification 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-171">StrongNameSignatureVerification Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 <span data-ttu-id="c1345-172">获取一个值，该值在提供的路径的程序集清单是否包含强名称签名，验证根据指定的标志。</span><span class="sxs-lookup"><span data-stu-id="c1345-172">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="c1345-173">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-173">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-174">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-174">StrongNameSignatureVerificationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="c1345-175">获取一个值，该值在提供的路径的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="c1345-175">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="c1345-176">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-176">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-177">StrongNameSignatureVerificationFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-177">StrongNameSignatureVerificationFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="c1345-178">验证已映射到内存的程序集关联的公钥无效。</span><span class="sxs-lookup"><span data-stu-id="c1345-178">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="c1345-179">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-179">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-180">StrongNameTokenFromAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-180">StrongNameTokenFromAssembly Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 <span data-ttu-id="c1345-181">从指定的程序集文件中创建强名称标记。</span><span class="sxs-lookup"><span data-stu-id="c1345-181">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="c1345-182">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-182">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-183">StrongNameTokenFromAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-183">StrongNameTokenFromAssemblyEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="c1345-184">从指定的程序集文件中，创建强名称标记并返回公钥。</span><span class="sxs-lookup"><span data-stu-id="c1345-184">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="c1345-185">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-185">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-186">StrongNameTokenFromPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="c1345-186">StrongNameTokenFromPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="c1345-187">获取表示公钥的标记。</span><span class="sxs-lookup"><span data-stu-id="c1345-187">Gets a token representing a public key.</span></span> <span data-ttu-id="c1345-188">从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1345-188">Deprecated starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="c1345-189">强命名结构</span><span class="sxs-lookup"><span data-stu-id="c1345-189">Strong Naming Structure</span></span>](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 <span data-ttu-id="c1345-190">描述强命名 API 用于管理强名称签名的程序集的非托管的结构...</span><span class="sxs-lookup"><span data-stu-id="c1345-190">Describes the unmanaged structure that the strong naming API uses  to administer strong name signing for assemblies..</span></span>  
  
 [<span data-ttu-id="c1345-191">PublicKeyBlob 结构</span><span class="sxs-lookup"><span data-stu-id="c1345-191">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 <span data-ttu-id="c1345-192">表示二进制格式公钥/私钥对的公钥。</span><span class="sxs-lookup"><span data-stu-id="c1345-192">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1345-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1345-193">See Also</span></span>  
 [<span data-ttu-id="c1345-194">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="c1345-194">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="c1345-195">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="c1345-195">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
