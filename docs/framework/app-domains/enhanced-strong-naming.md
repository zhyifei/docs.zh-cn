---
title: 改进的强命名
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 882b1de4b1fd3b013b6b2825aec5e607a387531b
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377992"
---
# <a name="enhanced-strong-naming"></a><span data-ttu-id="891eb-102">改进的强命名</span><span class="sxs-lookup"><span data-stu-id="891eb-102">Enhanced Strong Naming</span></span>
<span data-ttu-id="891eb-103">强名称签名是 .NET Framework 中用于识别程序集的识别机制。</span><span class="sxs-lookup"><span data-stu-id="891eb-103">A strong name signature is an identity mechanism in the .NET Framework for identifying assemblies.</span></span> <span data-ttu-id="891eb-104">它是一个公钥数字签名，通常用于验证发信方（签名方）发送给收信方（验证方）的数据的完整性。</span><span class="sxs-lookup"><span data-stu-id="891eb-104">It is a public-key digital signature that is typically used to verify the integrity of data being passed from an originator (signer) to a recipient (verifier).</span></span> <span data-ttu-id="891eb-105">此签名是程序集的唯一标识，可确保对程序集的引用清楚明确。</span><span class="sxs-lookup"><span data-stu-id="891eb-105">This signature is used as a unique identity for an assembly and ensures that references to the assembly are not ambiguous.</span></span> <span data-ttu-id="891eb-106">在生成过程中对程序集进行签名，然后在加载程序集时对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="891eb-106">The assembly is signed as part of the build process and then verified when it is loaded.</span></span>  
  
 <span data-ttu-id="891eb-107">强名称签名有助于防止恶意方篡改程序集，然后使用原始签名方的密钥对程序集进行重新签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-107">Strong name signatures help prevent malicious parties from tampering with an assembly and then re-signing the assembly with the original signer’s key.</span></span> <span data-ttu-id="891eb-108">但是强名称密钥不包含任何有关发布服务器的可靠信息，也不包含任何证书层次结构。</span><span class="sxs-lookup"><span data-stu-id="891eb-108">However, strong name keys don’t contain any reliable information about the publisher, nor do they contain a certificate hierarchy.</span></span> <span data-ttu-id="891eb-109">强名称签名不保证为程序集签名的人员的可信度，也不指示该人员是否为密钥的合法所有者；它仅指示密钥所有者对程序集进行了签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-109">A strong name signature does not guarantee the trustworthiness of the person who signed the assembly or indicate whether that person was a legitimate owner of the key; it indicates only that the owner of the key signed the assembly.</span></span> <span data-ttu-id="891eb-110">因此，不建议使用强名称签名作为判断是否应信任第三方代码的安全验证程序。</span><span class="sxs-lookup"><span data-stu-id="891eb-110">Therefore, we do not recommend using a strong name signature as a security validator for trusting third-party code.</span></span> <span data-ttu-id="891eb-111">建议使用 Microsoft Authenticode 对代码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="891eb-111">Microsoft Authenticode is the recommended way to authenticate code.</span></span>  
  
## <a name="limitations-of-conventional-strong-names"></a><span data-ttu-id="891eb-112">传统的强名称的限制</span><span class="sxs-lookup"><span data-stu-id="891eb-112">Limitations of Conventional Strong Names</span></span>  
 <span data-ttu-id="891eb-113">在早于 .NET Framework 4.5 的版本中使用强命名技术有以下缺点：</span><span class="sxs-lookup"><span data-stu-id="891eb-113">The strong naming technology used in versions before the .NET Framework 4.5 has the following shortcomings:</span></span>  
  
- <span data-ttu-id="891eb-114">密钥会不断受到攻击，并且技术和硬件的改进让根据公钥推断私钥变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="891eb-114">Keys are constantly under attack, and improved techniques and hardware make it easier to infer a private key from a public key.</span></span> <span data-ttu-id="891eb-115">抵御攻击需要使用更大的密钥。</span><span class="sxs-lookup"><span data-stu-id="891eb-115">To guard against attacks, larger keys are necessary.</span></span> <span data-ttu-id="891eb-116">早于 .NET Framework 4.5 的 .NET Framework 版本可以使用任意大小的密钥进行签名（默认大小为 1024 位），但是使用新密钥对程序集签名会破坏引用程序集旧标识的所有二进制文件。</span><span class="sxs-lookup"><span data-stu-id="891eb-116">.NET Framework versions before the .NET Framework 4.5 provide the ability to sign with any size key (the default size is 1024 bits), but signing an assembly with a new key breaks all binaries that reference the older identity of the assembly.</span></span> <span data-ttu-id="891eb-117">因此，如果想要保持兼容性，就很难升级签名密钥的大小。</span><span class="sxs-lookup"><span data-stu-id="891eb-117">Therefore, it is extremely difficult to upgrade the size of a signing key if you want to maintain compatibility.</span></span>  
  
- <span data-ttu-id="891eb-118">强名称签名仅支持 SHA-1 算法。</span><span class="sxs-lookup"><span data-stu-id="891eb-118">Strong name signing supports only the SHA-1 algorithm.</span></span> <span data-ttu-id="891eb-119">人们最近发现 SHA-1 不足以保证哈希应用程序的安全。</span><span class="sxs-lookup"><span data-stu-id="891eb-119">SHA-1 has recently been found to be inadequate for secure hashing applications.</span></span> <span data-ttu-id="891eb-120">因此需要使用更强的算法（SHA-256 或更高）。</span><span class="sxs-lookup"><span data-stu-id="891eb-120">Therefore, a stronger algorithm (SHA-256 or greater) is necessary.</span></span> <span data-ttu-id="891eb-121">SHA-1 可能不再与 FIPS 兼容，这样的话选择只使用与 FIPS 兼容的软件和算法的用户可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="891eb-121">It is possible that SHA-1 will lose its FIPS-compliant standing, which would present problems for those who choose to use only FIPS-compliant software and algorithms.</span></span>  
  
## <a name="advantages-of-enhanced-strong-names"></a><span data-ttu-id="891eb-122">增强的强名称的优点</span><span class="sxs-lookup"><span data-stu-id="891eb-122">Advantages of Enhanced Strong Names</span></span>  
 <span data-ttu-id="891eb-123">增强的强名称最主要的优势是与预先存在的强名称兼容，并且能够声明一个标识等效于另一个标识：</span><span class="sxs-lookup"><span data-stu-id="891eb-123">The main advantages of enhanced strong names are compatibility with pre-existing strong names and the ability to claim that one identity is equivalent to another:</span></span>  
  
- <span data-ttu-id="891eb-124">具有现有已签名程序集的开发人员可以将其标识迁移到 SHA-2 算法，同时兼容引用旧标识的程序集。</span><span class="sxs-lookup"><span data-stu-id="891eb-124">Developers who have pre-existing signed assemblies can migrate their identities to the SHA-2 algorithms while maintaining compatibility with assemblies that reference the old identities.</span></span>  
  
- <span data-ttu-id="891eb-125">创建新的程序集并且不考虑已有的强名称签名的开发人员可以使用安全性更高的 SHA-2 算法，并按惯用的方式对程序集签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-125">Developers who create new assemblies and are not concerned with pre-existing strong name signatures can use the more secure SHA-2 algorithms and sign the assemblies as they always have.</span></span>  
  
## <a name="using-enhanced-strong-names"></a><span data-ttu-id="891eb-126">使用改进的强名称</span><span class="sxs-lookup"><span data-stu-id="891eb-126">Using Enhanced Strong Names</span></span>  
 <span data-ttu-id="891eb-127">强名称密钥包含签名密钥和标识密钥。</span><span class="sxs-lookup"><span data-stu-id="891eb-127">Strong name keys consist of a signature key and an identity key.</span></span> <span data-ttu-id="891eb-128">使用签名密钥对程序集进行签名，使用标识密钥标识该程序集。</span><span class="sxs-lookup"><span data-stu-id="891eb-128">The assembly is signed with the signature key and is identified by the identity key.</span></span> <span data-ttu-id="891eb-129">在 .NET Framework 4.5 之前，这两个密钥相同。</span><span class="sxs-lookup"><span data-stu-id="891eb-129">Prior to the .NET Framework 4.5, these two keys were identical.</span></span> <span data-ttu-id="891eb-130">从 .NET Framework 4.5 开始，标识密钥与早期 .NET Framework 版本中的相同，但是签名密钥使用了更强的哈希算法进行了改进。</span><span class="sxs-lookup"><span data-stu-id="891eb-130">Starting with the .NET Framework 4.5, the identity key remains the same as in earlier .NET Framework versions, but the signature key is enhanced with a stronger hash algorithm.</span></span> <span data-ttu-id="891eb-131">此外，使用标识密钥对签名密钥进行签名以创建副署。</span><span class="sxs-lookup"><span data-stu-id="891eb-131">In addition, the signature key is signed with the identity key to create a counter-signature.</span></span>  
  
 <span data-ttu-id="891eb-132">通过 <xref:System.Reflection.AssemblySignatureKeyAttribute> 属性，程序集元数据可将已有公钥用于程序集标识，让旧程序集引用仍然有效。</span><span class="sxs-lookup"><span data-stu-id="891eb-132">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute enables the assembly metadata to use the pre-existing public key for assembly identity, which allows old assembly references to continue to work.</span></span>  <span data-ttu-id="891eb-133"><xref:System.Reflection.AssemblySignatureKeyAttribute> 使用副署来确保新签名密钥的所有者同时也是旧标识密钥的所有者。</span><span class="sxs-lookup"><span data-stu-id="891eb-133">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute uses the counter-signature to ensure that the owner of the new signature key is also the owner of the old identity key.</span></span>  
  
### <a name="signing-with-sha-2-without-key-migration"></a><span data-ttu-id="891eb-134">使用 SHA-2 签名，但不进行密钥迁移</span><span class="sxs-lookup"><span data-stu-id="891eb-134">Signing with SHA-2, Without Key Migration</span></span>  
 <span data-ttu-id="891eb-135">在命令提示符窗口中运行以下命令，在不迁移强名称签名的情况下对程序集签名：</span><span class="sxs-lookup"><span data-stu-id="891eb-135">Run the following commands from a Command Prompt window to sign an assembly without migrating a strong name signature:</span></span>  
  
1. <span data-ttu-id="891eb-136">生成新的标识密钥（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="891eb-136">Generate the new identity key (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2. <span data-ttu-id="891eb-137">提取标识公钥，并指定使用此密钥进行签名时，须使用 SHA-2 算法。</span><span class="sxs-lookup"><span data-stu-id="891eb-137">Extract the identity public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3. <span data-ttu-id="891eb-138">使用标识公钥文件对程序集进行延迟签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-138">Delay-sign the assembly with the identity public key file.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4. <span data-ttu-id="891eb-139">使用完整标识密钥对对程序集进行重新签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-139">Re-sign the assembly with the full identity key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a><span data-ttu-id="891eb-140">使用 SHA-2 签名，并进行密钥迁移</span><span class="sxs-lookup"><span data-stu-id="891eb-140">Signing with SHA-2, with Key Migration</span></span>  
 <span data-ttu-id="891eb-141">在命令提示符窗口中运行以下命令，使用迁移的强名称签名对程序集签名：</span><span class="sxs-lookup"><span data-stu-id="891eb-141">Run the following commands from a Command Prompt window to sign an assembly with a migrated strong name signature.</span></span>  
  
1. <span data-ttu-id="891eb-142">生成标识密钥和签名密钥对（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="891eb-142">Generate an identity and signature key pair (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2. <span data-ttu-id="891eb-143">提取签名公钥，并指定使用此密钥进行签名时，必须使用 SHA-2 算法。</span><span class="sxs-lookup"><span data-stu-id="891eb-143">Extract the signature public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3. <span data-ttu-id="891eb-144">提取标识公钥，该公钥确定用于生成副署的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="891eb-144">Extract the identity public key, which determines the hash algorithm that generates a counter-signature.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4. <span data-ttu-id="891eb-145">生成 <xref:System.Reflection.AssemblySignatureKeyAttribute> 属性的参数，并将该参数附加到程序集。</span><span class="sxs-lookup"><span data-stu-id="891eb-145">Generate the parameters for a <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute, and attach the attribute to the assembly.</span></span>  
  
    ```  
    sn -a IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  

    <span data-ttu-id="891eb-146">这将生成类似下面的输出。</span><span class="sxs-lookup"><span data-stu-id="891eb-146">This produces output similar to the following.</span></span>

    ```
    Information for key migration attribute.
    (System.Reflection.AssemblySignatureKeyAttribute):
    publicKey=
    002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519
    d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936
    e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b4
    3893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a3
    4d153cdd

    counterSignature=
    e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91eb
    e1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8
    ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3
    ae5fec2c682e57b7442738
    ```

    <span data-ttu-id="891eb-147">然后可以将此输出转换为 AssemblySignatureKeyAttribute。</span><span class="sxs-lookup"><span data-stu-id="891eb-147">This output can then be transformed into an AssemblySignatureKeyAttribute.</span></span>

    ```
    [assembly:System.Reflection.AssemblySignatureKeyAttribute(
    "002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b43893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a34d153cdd",
    "e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91ebe1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3ae5fec2c682e57b7442738"
    )]
    ```
  
5. <span data-ttu-id="891eb-148">使用标识公钥延迟对程序集签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-148">Delay-sign the assembly with the identity public key.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6. <span data-ttu-id="891eb-149">使用签名密钥对对程序集进行完整签名。</span><span class="sxs-lookup"><span data-stu-id="891eb-149">Fully sign the assembly with the signature key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="891eb-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="891eb-150">See also</span></span>

- [<span data-ttu-id="891eb-151">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="891eb-151">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
