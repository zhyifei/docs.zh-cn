---
title: "创建和使用具有强名称的程序集"
ms.date: 08/01/2017
ms.prod: .net-framework
ms.technology: dotnet-bcl
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, about strong-named assemblies
- strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, scenarios
- assemblies [.NET Framework], strong-named
- strong-named assemblies, loading into trusted application domains
- assembly binding, strong-named
ms.assetid: ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39fbd38549a791a761c633dca90dbdeeeefce10b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-and-using-strong-named-assemblies"></a><span data-ttu-id="841b8-102">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="841b8-102">Creating and Using Strong-Named Assemblies</span></span>
<a name="top"></a><span data-ttu-id="841b8-103">强名称是由程序集的标识加上公钥和数字签名组成的。其中，程序集的标识包括简单文本名称、版本号和区域性信息（如果提供的话）。</span><span class="sxs-lookup"><span data-stu-id="841b8-103">A strong name consists of the assembly's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="841b8-104">它使用相应私钥从程序集文件生成。</span><span class="sxs-lookup"><span data-stu-id="841b8-104">It is generated from an assembly file using the corresponding private key.</span></span> <span data-ttu-id="841b8-105">（程序集文件包含程序集清单，该清单包含组成程序集的所有文件的名称和哈希。）</span><span class="sxs-lookup"><span data-stu-id="841b8-105">(The assembly file contains the assembly manifest, which contains the names and hashes of all the files that make up the assembly.)</span></span>  
  
 <span data-ttu-id="841b8-106">具有强名称的程序集只能使用其他具有强名称的程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="841b8-106">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="841b8-107">否则，将会危害强名称程序集的完整性。</span><span class="sxs-lookup"><span data-stu-id="841b8-107">Otherwise, the integrity of the strong-named assembly would be compromised.</span></span>  
  
 <span data-ttu-id="841b8-108">本概述包含以下几节：</span><span class="sxs-lookup"><span data-stu-id="841b8-108">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="841b8-109">强名称方案</span><span class="sxs-lookup"><span data-stu-id="841b8-109">Strong Name Scenario</span></span>](#strong_name_scenario)  
  
-   [<span data-ttu-id="841b8-110">跳过受信任程序集的签名验证</span><span class="sxs-lookup"><span data-stu-id="841b8-110">Bypassing Signature Verification of Trusted Assemblies</span></span>](#bypassing_signature_verification)  
  
-   [<span data-ttu-id="841b8-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="841b8-111">Related Topics</span></span>](#related_topics)  
  
<a name="strong_name_scenario"></a>   
## <a name="strong-name-scenario"></a><span data-ttu-id="841b8-112">强名称方案</span><span class="sxs-lookup"><span data-stu-id="841b8-112">Strong Name Scenario</span></span>  
 <span data-ttu-id="841b8-113">下面的方案概述了对具有强名称的程序集进行签名以及稍后使用该名称对其进行引用的过程。</span><span class="sxs-lookup"><span data-stu-id="841b8-113">The following scenario outlines the process of signing an assembly with a strong name and later referencing it by that name.</span></span>  
  
1.  <span data-ttu-id="841b8-114">使用以下方法之一创建具有强名称的程序集 A：</span><span class="sxs-lookup"><span data-stu-id="841b8-114">Assembly A is created with a strong name using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="841b8-115">使用支持创建强名称的开发环境，如 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="841b8-115">Using a development environment that supports creating strong names, such as [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
    -   <span data-ttu-id="841b8-116">使用[强名称工具 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 创建加密密钥对，并使用命令行编译器或[程序集链接器 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 将密钥对分配到程序集。</span><span class="sxs-lookup"><span data-stu-id="841b8-116">Creating a cryptographic key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) and assigning that key pair to the assembly using either a command-line compiler or the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="841b8-117">Windows 软件开发工具包 (SDK) 同时提供 Sn.exe 和 Al.exe。</span><span class="sxs-lookup"><span data-stu-id="841b8-117">The Windows Software Development Kit (SDK) provides both Sn.exe and Al.exe.</span></span>  
  
2.  <span data-ttu-id="841b8-118">开发环境或工具对包含具有开发人员私钥的程序集清单的文件的哈希进行签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-118">The development environment or tool signs the hash of the file containing the assembly's manifest with the developer's private key.</span></span> <span data-ttu-id="841b8-119">此数字签名存储在包含程序集 A 的清单的可移植可执行 (PE) 文件中。</span><span class="sxs-lookup"><span data-stu-id="841b8-119">This digital signature is stored in the portable executable (PE) file that contains Assembly A's manifest.</span></span>  
  
3.  <span data-ttu-id="841b8-120">程序集 B 是程序集 A 的一个使用者。程序集 B 清单的引用部分包含表示程序集 A 公钥的标记。</span><span class="sxs-lookup"><span data-stu-id="841b8-120">Assembly B is a consumer of Assembly A. The reference section of Assembly B's manifest includes a token that represents Assembly A's public key.</span></span> <span data-ttu-id="841b8-121">标记是完整公钥的一部分，并且使用它而不是密钥本身以节省空间。</span><span class="sxs-lookup"><span data-stu-id="841b8-121">A token is a portion of the full public key and is used rather than the key itself to save space.</span></span>  
  
4.  <span data-ttu-id="841b8-122">当程序集放置在全局程序集缓存中时，公共语言运行时验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-122">The common language runtime verifies the strong name signature when the assembly is placed in the global assembly cache.</span></span> <span data-ttu-id="841b8-123">在运行时按强名称绑定时，公共语言运行时会将存储在程序集 B 的清单中的密钥与为程序集 A 生成强名称的密钥进行比较。如果 .NET Framework 安全检查通过且绑定成功，程序集 B 就可保证程序集 A 的位未被篡改，且这些位确实来自程序集 A 的开发人员。</span><span class="sxs-lookup"><span data-stu-id="841b8-123">When binding by strong name at run time, the common language runtime compares the key stored in Assembly B's manifest with the key used to generate the strong name for Assembly A. If the .NET Framework security checks pass and the bind succeeds, Assembly B has a guarantee that Assembly A's bits have not been tampered with and that these bits actually come from the developers of Assembly A.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="841b8-124">此方案不解决信任问题。</span><span class="sxs-lookup"><span data-stu-id="841b8-124">This scenario doesn't address trust issues.</span></span> <span data-ttu-id="841b8-125">除强名称外，程序集可携带完整的 Microsoft Authenticode 签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-125">Assemblies can carry full Microsoft Authenticode signatures in addition to a strong name.</span></span> <span data-ttu-id="841b8-126">Authenticode 签名包括建立信任的证书。</span><span class="sxs-lookup"><span data-stu-id="841b8-126">Authenticode signatures include a certificate that establishes trust.</span></span> <span data-ttu-id="841b8-127">请务必注意强名称不要求代码以这种方式进行签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-127">It's important to note that strong names don't require code to be signed in this way.</span></span> <span data-ttu-id="841b8-128">强名称仅提供唯一的标识。</span><span class="sxs-lookup"><span data-stu-id="841b8-128">Strong names only provide a unique identity.</span></span>  
  
 [<span data-ttu-id="841b8-129">返回页首</span><span class="sxs-lookup"><span data-stu-id="841b8-129">Back to top</span></span>](#top)  
  
<a name="bypassing_signature_verification"></a>   
## <a name="bypassing-signature-verification-of-trusted-assemblies"></a><span data-ttu-id="841b8-130">跳过受信任程序集的签名验证</span><span class="sxs-lookup"><span data-stu-id="841b8-130">Bypassing Signature Verification of Trusted Assemblies</span></span>  
 <span data-ttu-id="841b8-131">从 [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)]开始，当程序集加载到完全信任的应用程序域（如 `MyComputer` 区域的默认应用程序域）时，不会验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-131">Starting with the [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)], strong-name signatures are not validated when an assembly is loaded into a full-trust application domain, such as the default application domain for the `MyComputer` zone.</span></span> <span data-ttu-id="841b8-132">这被称之为强名称跳过功能。</span><span class="sxs-lookup"><span data-stu-id="841b8-132">This is referred to as the strong-name bypass feature.</span></span> <span data-ttu-id="841b8-133">在完全信任的环境中，对于已签名的完全信任的程序集，对 <xref:System.Security.Permissions.StrongNameIdentityPermission> 的需求总是成功，而不考虑其签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-133">In a full-trust environment, demands for <xref:System.Security.Permissions.StrongNameIdentityPermission> always succeed for signed, full-trust assemblies, regardless of their signature.</span></span> <span data-ttu-id="841b8-134">这种情况下，强名称跳过功能可避免完全信任程序集不必要的强名称签名验证开销，允许更快地加载程序集。</span><span class="sxs-lookup"><span data-stu-id="841b8-134">The strong-name bypass feature avoids the unnecessary overhead of strong-name signature verification of full-trust assemblies in this situation, allowing the assemblies to load faster.</span></span>  
  
 <span data-ttu-id="841b8-135">跳过功能适用于使用强名称进行签名及具有以下特征的任何程序集：</span><span class="sxs-lookup"><span data-stu-id="841b8-135">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="841b8-136">完全受信任，无需 <xref:System.Security.Policy.StrongName> 证据（如具有 `MyComputer` 区域证据）。</span><span class="sxs-lookup"><span data-stu-id="841b8-136">Fully trusted without <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="841b8-137">加载到完全受信任的 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="841b8-137">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="841b8-138">加载自该 <xref:System.AppDomain> 的 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性下的某个位置。</span><span class="sxs-lookup"><span data-stu-id="841b8-138">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="841b8-139">签名没有延迟。</span><span class="sxs-lookup"><span data-stu-id="841b8-139">Not delay-signed.</span></span>  
  
 <span data-ttu-id="841b8-140">可为单个应用程序或计算机禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="841b8-140">This feature can be disabled for individual applications or for a computer.</span></span> <span data-ttu-id="841b8-141">请参阅[如何：禁用强名称跳过功能](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)。</span><span class="sxs-lookup"><span data-stu-id="841b8-141">See [How to: Disable the Strong-Name Bypass Feature](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
 [<span data-ttu-id="841b8-142">返回页首</span><span class="sxs-lookup"><span data-stu-id="841b8-142">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="841b8-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="841b8-143">Related Topics</span></span>  
  
|<span data-ttu-id="841b8-144">标题</span><span class="sxs-lookup"><span data-stu-id="841b8-144">Title</span></span>|<span data-ttu-id="841b8-145">说明</span><span class="sxs-lookup"><span data-stu-id="841b8-145">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="841b8-146">如何：创建公钥/私钥对</span><span class="sxs-lookup"><span data-stu-id="841b8-146">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)|<span data-ttu-id="841b8-147">描述如何创建加密密钥对以对程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-147">Describes how to create a cryptographic key pair for signing an assembly.</span></span>|  
|[<span data-ttu-id="841b8-148">如何：使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="841b8-148">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)|<span data-ttu-id="841b8-149">介绍如何创建具有强名称的程序集。</span><span class="sxs-lookup"><span data-stu-id="841b8-149">Describes how to create a strong-named assembly.</span></span>|  
|[<span data-ttu-id="841b8-150">改进的强命名</span><span class="sxs-lookup"><span data-stu-id="841b8-150">Enhanced Strong Naming</span></span>](../../../docs/framework/app-domains/enhanced-strong-naming.md)|<span data-ttu-id="841b8-151">描述 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中强名称的改进。</span><span class="sxs-lookup"><span data-stu-id="841b8-151">Describes enhancements to strong-names in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|[<span data-ttu-id="841b8-152">如何：引用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="841b8-152">How to: Reference a Strong-Named Assembly</span></span>](../../../docs/framework/app-domains/how-to-reference-a-strong-named-assembly.md)|<span data-ttu-id="841b8-153">介绍如何在编译时或运行时引用具有强名称的程序集中的类型或资源。</span><span class="sxs-lookup"><span data-stu-id="841b8-153">Describes how to reference types or resources in a strong-named assembly at compile time or run time.</span></span>|  
|[<span data-ttu-id="841b8-154">如何：禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="841b8-154">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)|<span data-ttu-id="841b8-155">描述如何禁用跳过强名称签名验证的功能。</span><span class="sxs-lookup"><span data-stu-id="841b8-155">Describes how to disable the feature that bypasses the validation of strong-name signatures.</span></span> <span data-ttu-id="841b8-156">可为所有或特定应用程序禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="841b8-156">This feature can be disabled for all or for specific applications.</span></span>|  
|[<span data-ttu-id="841b8-157">创建程序集</span><span class="sxs-lookup"><span data-stu-id="841b8-157">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)|<span data-ttu-id="841b8-158">提供单个文件和多文件程序集的概述。</span><span class="sxs-lookup"><span data-stu-id="841b8-158">Provides an overview of single-file and multifile assemblies.</span></span>|  
|[<span data-ttu-id="841b8-159">如何在 Visual Studio 中延迟对程序集的签名</span><span class="sxs-lookup"><span data-stu-id="841b8-159">How to Delay Sign an Assembly in Visual Studio</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing#how-to-sign-an-assembly-in-visual-studio)|<span data-ttu-id="841b8-160">说明如何在创建程序集后对具有强名称的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="841b8-160">Explains how to sign an assembly with a strong name after the assembly has been created.</span></span>|  
|[<span data-ttu-id="841b8-161">Sn.exe（强名称工具）</span><span class="sxs-lookup"><span data-stu-id="841b8-161">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)|<span data-ttu-id="841b8-162">介绍 .NET Framework 中包含的可帮助创建具有强名称的程序集的工具。</span><span class="sxs-lookup"><span data-stu-id="841b8-162">Describes the tool included in the .NET Framework that helps create assemblies with strong names.</span></span> <span data-ttu-id="841b8-163">此工具提供有关密钥管理、签名生成和签名验证的选项。</span><span class="sxs-lookup"><span data-stu-id="841b8-163">This tool provides options for key management, signature generation, and signature verification.</span></span>|  
|[<span data-ttu-id="841b8-164">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="841b8-164">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)|<span data-ttu-id="841b8-165">介绍 .NET Framework 中包含的一种工具，该工具可生成具有模块或资源文件的程序集清单的文件。</span><span class="sxs-lookup"><span data-stu-id="841b8-165">Describes the tool included in the .NET Framework that generates a file that has an assembly manifest from modules or resource files.</span></span>|
