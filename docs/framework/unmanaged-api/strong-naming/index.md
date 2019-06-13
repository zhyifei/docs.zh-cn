---
title: 强命名（非托管 API 参考）
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ee08e9ca243ac086a0b75892bf9258246e8fd7c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490671"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="4f964-102">强命名（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="4f964-102">Strong Naming (Unmanaged API Reference)</span></span>
<span data-ttu-id="4f964-103">强命名 API 允许客户端管理程序集的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4f964-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="4f964-104">使用强名称对程序集进行签名将向包含程序集清单的文件添加公钥加密。</span><span class="sxs-lookup"><span data-stu-id="4f964-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="4f964-105">强名称签名帮助验证名称的唯一性，避免名称欺骗，并在解析引用时向调用方提供唯一标识。</span><span class="sxs-lookup"><span data-stu-id="4f964-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="4f964-106">但是，任何信任级别都不会与强名称关联。</span><span class="sxs-lookup"><span data-stu-id="4f964-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f964-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="4f964-107">In This Section</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f964-108">从 .NET Framework 4 开始，所有这些函数都已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-108">All of these functions have been deprecated starting with the .NET Framework 4.</span></span> <span data-ttu-id="4f964-109">有关建议的替代方案，请参阅 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="4f964-109">For suggested alternatives, see the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="4f964-110">GetHashFromAssemblyFile 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-110">GetHashFromAssemblyFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 <span data-ttu-id="4f964-111">使用指定的哈希算法获取指定程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="4f964-111">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="4f964-112">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-112">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-113">GetHashFromAssemblyFileW 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-113">GetHashFromAssemblyFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="4f964-114">使用指定的哈希算法获取指定为 Unicode 字符串的程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="4f964-114">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="4f964-115">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-115">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-116">GetHashFromBlob 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-116">GetHashFromBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 <span data-ttu-id="4f964-117">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="4f964-117">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="4f964-118">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-118">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-119">GetHashFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-119">GetHashFromFile Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 <span data-ttu-id="4f964-120">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="4f964-120">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="4f964-121">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-121">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-122">GetHashFromFileW 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-122">GetHashFromFileW Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 <span data-ttu-id="4f964-123">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="4f964-123">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="4f964-124">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-124">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-125">GetHashFromHandle 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-125">GetHashFromHandle Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 <span data-ttu-id="4f964-126">使用指定的哈希算法，生成具有指定文件句柄的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="4f964-126">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="4f964-127">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-127">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-128">StrongNameCompareAssemblies 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-128">StrongNameCompareAssemblies Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 <span data-ttu-id="4f964-129">确定两个程序集是否仅是强名称签名不同。</span><span class="sxs-lookup"><span data-stu-id="4f964-129">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="4f964-130">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-130">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-131">StrongNameErrorInfo 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-131">StrongNameErrorInfo Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 <span data-ttu-id="4f964-132">获取由其中一个强名称函数引发的最后一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="4f964-132">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="4f964-133">StrongNameFreeBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-133">StrongNameFreeBuffer Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 <span data-ttu-id="4f964-134">释放先前调用 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) 或 [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md) 强名称函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="4f964-134">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="4f964-135">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-135">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-136">StrongNameGetBlob 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-136">StrongNameGetBlob Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 <span data-ttu-id="4f964-137">使用指定地址处可执行文件的二进制表示形式填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4f964-137">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="4f964-138">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-138">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-139">StrongNameGetBlobFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-139">StrongNameGetBlobFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="4f964-140">获取指定内存地址处程序集映像的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="4f964-140">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="4f964-141">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-141">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-142">StrongNameGetPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-142">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 <span data-ttu-id="4f964-143">从私钥/公钥对中获取公钥。</span><span class="sxs-lookup"><span data-stu-id="4f964-143">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="4f964-144">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-144">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-145">StrongNameHashSize 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-145">StrongNameHashSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 <span data-ttu-id="4f964-146">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="4f964-146">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="4f964-147">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-147">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-148">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-148">StrongNameKeyDelete Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 <span data-ttu-id="4f964-149">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="4f964-149">Deletes the specified key container.</span></span> <span data-ttu-id="4f964-150">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-150">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-151">StrongNameKeyGen 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-151">StrongNameKeyGen Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 <span data-ttu-id="4f964-152">创建新的公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="4f964-152">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="4f964-153">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-153">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-154">StrongNameKeyGenEx 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-154">StrongNameKeyGenEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 <span data-ttu-id="4f964-155">生成具有指定密钥大小的新公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="4f964-155">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="4f964-156">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-156">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-157">StrongNameKeyInstall 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-157">StrongNameKeyInstall Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 <span data-ttu-id="4f964-158">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="4f964-158">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="4f964-159">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-159">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-160">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-160">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="4f964-161">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4f964-161">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="4f964-162">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-162">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-163">StrongNameSignatureGenerationEx 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-163">StrongNameSignatureGenerationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="4f964-164">根据指定标志为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4f964-164">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="4f964-165">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-165">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-166">StrongNameSignatureSize 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-166">StrongNameSignatureSize Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 <span data-ttu-id="4f964-167">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="4f964-167">Returns the size of the strong name signature.</span></span> <span data-ttu-id="4f964-168">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-168">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-169">StrongNameSignatureVerification 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-169">StrongNameSignatureVerification Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 <span data-ttu-id="4f964-170">获取一个值，该值指示提供的路径中的程序集清单是否包含根据指定标志验证的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4f964-170">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="4f964-171">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-171">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-172">StrongNameSignatureVerificationEx 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-172">StrongNameSignatureVerificationEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="4f964-173">获取一个值，该值指示提供的路径中的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4f964-173">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="4f964-174">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-174">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-175">StrongNameSignatureVerificationFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-175">StrongNameSignatureVerificationFromImage Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="4f964-176">验证已映射到内存的程序集对关联的公钥是否有效。</span><span class="sxs-lookup"><span data-stu-id="4f964-176">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="4f964-177">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-177">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-178">StrongNameTokenFromAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-178">StrongNameTokenFromAssembly Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 <span data-ttu-id="4f964-179">从指定的程序集文件创建强名称令牌。</span><span class="sxs-lookup"><span data-stu-id="4f964-179">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="4f964-180">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-180">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-181">StrongNameTokenFromAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-181">StrongNameTokenFromAssemblyEx Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="4f964-182">从指定的程序集文件创建强名称令牌并返回公钥。</span><span class="sxs-lookup"><span data-stu-id="4f964-182">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="4f964-183">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-183">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-184">StrongNameTokenFromPublicKey 函数</span><span class="sxs-lookup"><span data-stu-id="4f964-184">StrongNameTokenFromPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="4f964-185">获取表示公钥的令牌。</span><span class="sxs-lookup"><span data-stu-id="4f964-185">Gets a token representing a public key.</span></span> <span data-ttu-id="4f964-186">从 .NET Framework 4 开始已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f964-186">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="4f964-187">PublicKeyBlob Strong Naming</span><span class="sxs-lookup"><span data-stu-id="4f964-187">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 <span data-ttu-id="4f964-188">表示二进制格式的公钥/私钥对中的公钥。</span><span class="sxs-lookup"><span data-stu-id="4f964-188">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f964-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f964-189">See also</span></span>

- [<span data-ttu-id="4f964-190">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="4f964-190">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="4f964-191">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="4f964-191">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
