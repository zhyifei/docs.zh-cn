---
title: "如何：创建发行者策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4ccd490f6d31ad1d20128497e5115147eddb3df4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="d8541-102">如何：创建发行者策略</span><span class="sxs-lookup"><span data-stu-id="d8541-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="d8541-103">程序集的供应商可以状态应用程序应使用通过包括发布服务器策略文件与已升级的程序集的程序集的较新版本。</span><span class="sxs-lookup"><span data-stu-id="d8541-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="d8541-104">发布服务器策略文件指定程序集重定向和基本代码设置，并为应用程序配置文件使用相同的格式。</span><span class="sxs-lookup"><span data-stu-id="d8541-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="d8541-105">发布服务器策略文件编译成程序集和放入全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="d8541-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="d8541-106">有三个步骤中创建发布服务器策略涉及：</span><span class="sxs-lookup"><span data-stu-id="d8541-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1.  <span data-ttu-id="d8541-107">创建发布服务器策略文件。</span><span class="sxs-lookup"><span data-stu-id="d8541-107">Create a publisher policy file.</span></span>  
  
2.  <span data-ttu-id="d8541-108">创建发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-108">Create a publisher policy assembly.</span></span>  
  
3.  <span data-ttu-id="d8541-109">将发行者策略程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="d8541-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="d8541-110">发布服务器策略的架构中所述[重定向程序集版本](../../../docs/framework/configure-apps/redirect-assembly-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="d8541-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="d8541-111">下面的示例说明了一个发行者策略文件，将重定向的一个版本`myAssembly`到另一个。</span><span class="sxs-lookup"><span data-stu-id="d8541-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d8541-112">若要了解如何指定基本代码，请参阅[指定程序集的位置](../../../docs/framework/configure-apps/specify-assembly-location.md)。</span><span class="sxs-lookup"><span data-stu-id="d8541-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="d8541-113">创建发行者策略程序集</span><span class="sxs-lookup"><span data-stu-id="d8541-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="d8541-114">使用[程序集链接器 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)创建发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="d8541-115">若要创建发行者策略程序集</span><span class="sxs-lookup"><span data-stu-id="d8541-115">To create a publisher policy assembly</span></span>  
  
1.  <span data-ttu-id="d8541-116">在命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8541-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="d8541-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="d8541-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="d8541-118">在此命令：</span><span class="sxs-lookup"><span data-stu-id="d8541-118">In this command:</span></span>  
  
    -   <span data-ttu-id="d8541-119">*PublisherPolicyFile*参数是发布服务器策略文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d8541-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="d8541-120">*PublisherPolicyAssemblyFile*参数是导致此命令的发行者策略程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="d8541-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="d8541-121">程序集文件名称必须遵循格式：</span><span class="sxs-lookup"><span data-stu-id="d8541-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="d8541-122">**策略。**</span><span class="sxs-lookup"><span data-stu-id="d8541-122">**policy.**</span></span> <span data-ttu-id="d8541-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="d8541-123">*majorNumber* **.**</span></span> <span data-ttu-id="d8541-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="d8541-124">*minorNumber* **.**</span></span> <span data-ttu-id="d8541-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="d8541-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="d8541-126">*KeyPairFile*参数是包含密钥对的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d8541-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="d8541-127">你必须签名的程序集和具有相同的密钥对的发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="d8541-128">*ProcessorArchitecture*参数标识的特定于处理器的程序集的目标平台。</span><span class="sxs-lookup"><span data-stu-id="d8541-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d8541-129">面向特定的处理器体系结构的能力是.NET Framework 2.0 版中新增功能。</span><span class="sxs-lookup"><span data-stu-id="d8541-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="d8541-130">下面的命令创建名为的发行者策略程序集`policy.1.0.myAssembly`从发布服务器策略文件调用`pub.config`，对使用的密钥对中的程序集分配强名称`sgKey.snk`文件中，并指定该程序集针对 x86处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="d8541-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="d8541-131">发行者策略程序集必须与它将应用于程序集的处理器体系结构匹配。</span><span class="sxs-lookup"><span data-stu-id="d8541-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="d8541-132">因此，如果你的程序集具有<xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>值<xref:System.Reflection.ProcessorArchitecture.MSIL>，该程序集的发布服务器策略程序集必须用来创建`/platform:anycpu`。</span><span class="sxs-lookup"><span data-stu-id="d8541-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="d8541-133">必须提供单独为每个特定于处理器的程序集的发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="d8541-134">此规则的结果是版本号的，若要更改的程序集的处理器体系结构，你必须更改的主要或次要组件，以便你可以提供具有正确的处理器体系结构的新发布服务器策略程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="d8541-135">程序集具有不同的处理器体系结构，旧的发行者策略程序集无法服务你的程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="d8541-136">另一个后果是版本 2.0 链接器不能用于创建编译使用早期版本的.NET Framework 中，因为它始终指定处理器体系结构的程序集的发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="d8541-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="d8541-137">将发行者策略程序集添加到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="d8541-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="d8541-138">使用[全局程序集缓存工具 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)将发行者策略程序集添加到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="d8541-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="d8541-139">若要将发行者策略程序集添加到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="d8541-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1.  <span data-ttu-id="d8541-140">在命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8541-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="d8541-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="d8541-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="d8541-142">以下命令将添加`policy.1.0.myAssembly.dll`到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="d8541-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d8541-143">无法将发行者策略程序集添加到全局程序集缓存中，除非原始发布服务器策略文件位于与程序集位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="d8541-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8541-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8541-144">See Also</span></span>  
 [<span data-ttu-id="d8541-145">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="d8541-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="d8541-146">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="d8541-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="d8541-147">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="d8541-147">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="d8541-148">配置.NET Framework 应用</span><span class="sxs-lookup"><span data-stu-id="d8541-148">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [<span data-ttu-id="d8541-149">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d8541-149">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d8541-150">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d8541-150">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="d8541-151">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="d8541-151">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
