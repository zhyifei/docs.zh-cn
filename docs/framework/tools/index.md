---
title: .NET Framework 工具
ms.date: 03/30/2017
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 208dc3048b52cc895a5142a7686829390d1d4503
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739433"
---
# <a name="net-framework-tools"></a><span data-ttu-id="11da1-102">.NET Framework 工具</span><span class="sxs-lookup"><span data-stu-id="11da1-102">.NET Framework Tools</span></span>
<span data-ttu-id="11da1-103">您可以使用 .NET Framework 工具轻松创建、部署和管理面向 .NET Framework 的应用程序和组件。</span><span class="sxs-lookup"><span data-stu-id="11da1-103">The .NET Framework tools make it easier for you to create, deploy, and manage applications and components that target the .NET Framework.</span></span>  
  
<span data-ttu-id="11da1-104">此节中介绍的大部分 .NET Framework 工具将自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="11da1-104">Most of the .NET Framework tools described in this section are automatically installed with Visual Studio.</span></span> <span data-ttu-id="11da1-105">Visual Studio 可从 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页面下载。</span><span class="sxs-lookup"><span data-stu-id="11da1-105">To download Visual Studio, visit the [Visual Studio Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) page.</span></span>
  
 <span data-ttu-id="11da1-106">可以从命令行运行除程序集缓存查看器 (Shfusion.dll) 之外的所有工具。</span><span class="sxs-lookup"><span data-stu-id="11da1-106">You can run all the tools from the command line with the exception of the Assembly Cache Viewer (Shfusion.dll).</span></span> <span data-ttu-id="11da1-107">必须从文件资源管理器访问 Shfusion.dll。</span><span class="sxs-lookup"><span data-stu-id="11da1-107">You must access Shfusion.dll from File Explorer.</span></span>  
  
 <span data-ttu-id="11da1-108">运行命令行工具的最佳方法是使用 Visual Studio 的开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="11da1-108">The best way to run the command-line tools is by using the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="11da1-109">您可以使用这些实用程序轻松运行工具，而不需要导航到安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="11da1-109">These utilities enable you to run the tools easily, without navigating to the installation folder.</span></span> <span data-ttu-id="11da1-110">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="11da1-110">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11da1-111">某些工具特定于 32 位或 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="11da1-111">Some tools are specific to either 32-bit computers or 64-bit computers.</span></span> <span data-ttu-id="11da1-112">确保为你的计算机运行适当的工具版本。</span><span class="sxs-lookup"><span data-stu-id="11da1-112">Be sure to run the appropriate version of the tool for your computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11da1-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="11da1-113">In This Section</span></span>  
 [<span data-ttu-id="11da1-114">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="11da1-114">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 <span data-ttu-id="11da1-115">从模块或资源文件中生成一个具有程序集清单的文件。</span><span class="sxs-lookup"><span data-stu-id="11da1-115">Generates a file that has an assembly manifest from modules or resource files.</span></span>  
  
 [<span data-ttu-id="11da1-116">Aximp.exe（Windows 窗体 ActiveX 控件导入程序）</span><span class="sxs-lookup"><span data-stu-id="11da1-116">Aximp.exe (Windows Forms ActiveX Control Importer)</span></span>](../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)  
 <span data-ttu-id="11da1-117">将 ActiveX 控件的 COM 类型库中的类型定义转换成 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="11da1-117">Converts type definitions in a COM type library for an ActiveX control into a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="11da1-118">Caspol.exe（代码访问安全策略工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-118">Caspol.exe (Code Access Security Policy Tool)</span></span>](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)  
 <span data-ttu-id="11da1-119">用于查看和配置计算机策略级别、用户策略级别和企业策略级别的安全策略。</span><span class="sxs-lookup"><span data-stu-id="11da1-119">Enables you to view and configure security policy for the machine policy level, the user policy level, and the enterprise policy level.</span></span> <span data-ttu-id="11da1-120">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 及更高版本中，此工具不会影响代码访问安全性 (CAS) 策略，除非 [\<legacyCasPolicy> 元素](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="11da1-120">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later, this tool does not affect code access security (CAS) policy unless the [\<legacyCasPolicy> element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) is set to `true`.</span></span> <span data-ttu-id="11da1-121">有关详细信息，请参阅[安全更改](../../../docs/framework/security/security-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="11da1-121">For more information, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 [<span data-ttu-id="11da1-122">Cert2spc.exe（软件发行者证书测试工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-122">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>](../../../docs/framework/tools/cert2spc-exe-software-publisher-certificate-test-tool.md)  
 <span data-ttu-id="11da1-123">通过一个或多个 X.509 证书创建发行者证书 (SPC)。</span><span class="sxs-lookup"><span data-stu-id="11da1-123">Creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="11da1-124">此工具仅用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="11da1-124">This tool is for testing purposes only.</span></span>  
  
 [<span data-ttu-id="11da1-125">Certmgr.exe（证书管理器工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-125">Certmgr.exe (Certificate Manager Tool)</span></span>](../../../docs/framework/tools/certmgr-exe-certificate-manager-tool.md)  
 <span data-ttu-id="11da1-126">管理证书、证书信任列表 (CTL) 和证书吊销列表 (CRL)。</span><span class="sxs-lookup"><span data-stu-id="11da1-126">Manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 [<span data-ttu-id="11da1-127">Clrver.exe（CLR 版本工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-127">Clrver.exe (CLR Version Tool)</span></span>](../../../docs/framework/tools/clrver-exe-clr-version-tool.md)  
 <span data-ttu-id="11da1-128">报告计算机上公共语言运行时 (CLR) 的所有已安装版本。</span><span class="sxs-lookup"><span data-stu-id="11da1-128">reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 [<span data-ttu-id="11da1-129">CorFlags.exe（CorFlags 转换工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-129">CorFlags.exe (CorFlags Conversion Tool)</span></span>](../../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md)  
 <span data-ttu-id="11da1-130">可用于配置可移植可执行 (PE) 映像的标头的 CorFlags 部分。</span><span class="sxs-lookup"><span data-stu-id="11da1-130">Lets you configure the CorFlags section of the header of a portable executable (PE) image.</span></span>  
  
 [<span data-ttu-id="11da1-131">Fuslogvw.exe（程序集绑定日志查看器）</span><span class="sxs-lookup"><span data-stu-id="11da1-131">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)  
 <span data-ttu-id="11da1-132">显示有关程序集绑定的信息，以帮助您诊断 .NET Framework 无法在运行时定位某个程序集的原因。</span><span class="sxs-lookup"><span data-stu-id="11da1-132">Displays information about assembly binds to help you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span>  
  
 [<span data-ttu-id="11da1-133">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-133">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 <span data-ttu-id="11da1-134">可用于查看和操作全局程序集缓存和下载缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="11da1-134">Lets you view and manipulate the contents of the global assembly cache and download cache.</span></span>  
  
 [<span data-ttu-id="11da1-135">Ilasm.exe（IL 汇编程序）</span><span class="sxs-lookup"><span data-stu-id="11da1-135">Ilasm.exe (IL Assembler)</span></span>](../../../docs/framework/tools/ilasm-exe-il-assembler.md)  
 <span data-ttu-id="11da1-136">从中间语言 (IL) 生成可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="11da1-136">Generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="11da1-137">可以运行生成的可执行文件以确定 IL 是否按预期执行。</span><span class="sxs-lookup"><span data-stu-id="11da1-137">You can run the resulting executable to determine whether the IL performs as expected.</span></span>  
  
 [<span data-ttu-id="11da1-138">Ildasm.exe（IL 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="11da1-138">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)  
 <span data-ttu-id="11da1-139">采用包含中间语言 (IL) 代码的可移植可执行 (PE) 文件，并创建可作为 IL 汇编程序 (Ilasm.exe) 的输入的文本文件。</span><span class="sxs-lookup"><span data-stu-id="11da1-139">Takes a portable executable (PE) file that contains intermediate language (IL) code and creates a text file that can be input to the IL Assembler (Ilasm.exe).</span></span>  
  
 [<span data-ttu-id="11da1-140">Installutil.exe（安装程序工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-140">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)  
 <span data-ttu-id="11da1-141">可用于通过执行指定程序集中的安装程序组件，安装和卸载服务器资源。</span><span class="sxs-lookup"><span data-stu-id="11da1-141">Enables you to install and uninstall server resources by executing the installer components in a specified assembly.</span></span> <span data-ttu-id="11da1-142">（与 <xref:System.Configuration.Install> 命名空间中的类一起工作。）可用于通过执行指定程序集中的安装程序组件，安装和卸载服务器资源。</span><span class="sxs-lookup"><span data-stu-id="11da1-142">(Works with classes in the <xref:System.Configuration.Install> namespace.) Enables you to install and uninstall server resources by executing the installer components in a specified assembly.</span></span> <span data-ttu-id="11da1-143">（与 <xref:System.Configuration.Install> 命名空间中的类一起工作。）</span><span class="sxs-lookup"><span data-stu-id="11da1-143">(Works with classes in the <xref:System.Configuration.Install> namespace.)</span></span>  
  
 [<span data-ttu-id="11da1-144">Lc.exe（许可证编译器）</span><span class="sxs-lookup"><span data-stu-id="11da1-144">Lc.exe (License Compiler)</span></span>](../../../docs/framework/tools/lc-exe-license-compiler.md)  
 <span data-ttu-id="11da1-145">读取包含授权信息的文本文件，并生成一个可作为资源嵌入到公共语言运行时可执行文件中的 .licenses 文件。</span><span class="sxs-lookup"><span data-stu-id="11da1-145">Reads text files that contain licensing information and produces a .licenses file that can be embedded in a common language runtime executable as a resource.</span></span> <span data-ttu-id="11da1-146">读取包含授权信息的文本文件，并生成一个可作为资源嵌入到公共语言运行时可执行文件中的 .licenses 文件。</span><span class="sxs-lookup"><span data-stu-id="11da1-146">Reads text files that contain licensing information and produces a .licenses file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 [<span data-ttu-id="11da1-147">Mage.exe（清单生成和编辑工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-147">Mage.exe (Manifest Generation and Editing Tool)</span></span>](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 <span data-ttu-id="11da1-148">可用来创建、编辑应用程序和部署清单并为其签名。</span><span class="sxs-lookup"><span data-stu-id="11da1-148">Lets you create, edit, and sign application and deployment manifests.</span></span> <span data-ttu-id="11da1-149">作为命令行工具，Mage.exe 可以从批处理脚本和其他基于 Windows 的应用程序（包括 ASP.NET 应用程序）运行。</span><span class="sxs-lookup"><span data-stu-id="11da1-149">As a command-line tool, Mage.exe can be run from both batch scripts and other Windows-based applications, including ASP.NET applications.</span></span>  
  
 [<span data-ttu-id="11da1-150">MageUI.exe（图形化客户端中的清单生成和编辑工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-150">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
 <span data-ttu-id="11da1-151">支持命令行工具 Mage.exe 提供的相同功能，只不过使用了基于 Windows 的用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="11da1-151">Supports the same functionality as the command-line tool Mage.exe, but uses a Windows-based user interface (UI).</span></span> <span data-ttu-id="11da1-152">支持命令行工具 Mage.exe 提供的相同功能，只不过使用了基于 Windows 的用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="11da1-152">Supports the same functionality as the command-line tool Mage.exe, but uses a Windows-based user interface (UI).</span></span>  
  
 [<span data-ttu-id="11da1-153">MDbg.exe（.NET Framework 命令行调试程序）</span><span class="sxs-lookup"><span data-stu-id="11da1-153">MDbg.exe (.NET Framework Command-Line Debugger)</span></span>](../../../docs/framework/tools/mdbg-exe.md)  
 <span data-ttu-id="11da1-154">帮助工具供应商和应用程序开发人员可查找和修复面向 .NET Framework 公共语言运行时的程序中的 bug。</span><span class="sxs-lookup"><span data-stu-id="11da1-154">Helps tools vendors and application developers find and fix bugs in programs that target the .NET Framework common language runtime.</span></span> <span data-ttu-id="11da1-155">此工具使用运行时调试 API 提供调试服务。</span><span class="sxs-lookup"><span data-stu-id="11da1-155">This tool uses the runtime debugging API to provide debugging services.</span></span>  
  
 [<span data-ttu-id="11da1-156">Mgmtclassgen.exe（管理强类型类生成器）</span><span class="sxs-lookup"><span data-stu-id="11da1-156">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>](../../../docs/framework/tools/mgmtclassgen-exe.md)  
 <span data-ttu-id="11da1-157">可用于为指定的 Windows Management Instrumentation (WMI) 类生成早期绑定的托管类。</span><span class="sxs-lookup"><span data-stu-id="11da1-157">Enables you to generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span>  
  
 [<span data-ttu-id="11da1-158">Mpgo.exe（按托管配置文件优化工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-158">Mpgo.exe (Managed Profile Guided Optimization Tool)</span></span>](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)  
 <span data-ttu-id="11da1-159">使用公共最终用户方案，可以调整本机映像程序集。</span><span class="sxs-lookup"><span data-stu-id="11da1-159">Enables you to tune native image assemblies using common end-user scenarios.</span></span> <span data-ttu-id="11da1-160">利用 Mpgo.exe，可以通过使用应用程序开发人员选择的培训方案来为本机映像应用程序（而非 .NET Framework 程序集）生成和使用配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="11da1-160">Mpgo.exe allows the generation and consumption of profile data for native image application assemblies (not the .NET Framework assemblies) using training scenarios selected by the application developer.</span></span>  
  
 [<span data-ttu-id="11da1-161">Ngen.exe（本机映像生成器）</span><span class="sxs-lookup"><span data-stu-id="11da1-161">Ngen.exe (Native Image Generator)</span></span>](../../../docs/framework/tools/ngen-exe-native-image-generator.md)  
 <span data-ttu-id="11da1-162">通过使用本机映像（包含已编译的处理器专用机器代码的文件）来提高托管应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="11da1-162">Improves the performance of managed applications through the use of native images (files containing compiled processor-specific machine code).</span></span> <span data-ttu-id="11da1-163">运行时可从缓存中使用本机映像，而不必使用实时 (JIT) 编译器编译原始程序集。</span><span class="sxs-lookup"><span data-stu-id="11da1-163">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>  
  
 [<span data-ttu-id="11da1-164">Peverify.exe（PEVerify 工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-164">Peverify.exe (PEVerify Tool)</span></span>](../../../docs/framework/tools/peverify-exe-peverify-tool.md)  
 <span data-ttu-id="11da1-165">帮助验证 Microsoft 中间语言 (MSIL) 代码和关联的元数据是否满足类型安全要求。</span><span class="sxs-lookup"><span data-stu-id="11da1-165">Helps you verify whether your Microsoft intermediate language (MSIL) code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="11da1-166">帮助验证 Microsoft 中间语言 (MSIL) 代码和关联的元数据是否满足类型安全要求。</span><span class="sxs-lookup"><span data-stu-id="11da1-166">Helps you verify whether your Microsoft intermediate language (MSIL) code and associated metadata meet type safety requirements.</span></span>  
  
 [<span data-ttu-id="11da1-167">Regasm.exe（程序集注册工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-167">Regasm.exe (Assembly Registration Tool)</span></span>](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 <span data-ttu-id="11da1-168">读取程序集中的元数据，并在注册表中添加必要的项。</span><span class="sxs-lookup"><span data-stu-id="11da1-168">Reads the metadata within an assembly and adds the necessary entries to the registry.</span></span> <span data-ttu-id="11da1-169">这使 COM 客户端可以显示为 .NET Framework 类。</span><span class="sxs-lookup"><span data-stu-id="11da1-169">This enables COM clients to appear as .NET Framework classes.</span></span>  
  
 [<span data-ttu-id="11da1-170">Regsvcs.exe（.NET 服务安装工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-170">Regsvcs.exe (.NET Services Installation Tool)</span></span>](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md)  
 <span data-ttu-id="11da1-171">加载和注册程序集，生成类型库并将其安装到指定的 COM+ 1.0 版应用程序中，以及配置已通过编程方式添加到某个类的服务。</span><span class="sxs-lookup"><span data-stu-id="11da1-171">Loads and registers an assembly, generates and installs a type library into a specified COM+ version 1.0 application, and configures services that you have added programmatically to a class.</span></span>  
  
 [<span data-ttu-id="11da1-172">Resgen.exe（资源文件生成器）</span><span class="sxs-lookup"><span data-stu-id="11da1-172">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="11da1-173">将文本（.txt 或 .restext）文件和基于 XML 的资源格式 (.resx) 文件转换为公共语言运行时二进制 (.resources) 文件，这些 .resources 文件可嵌入到运行时二进制可执行文件中或编译到附属程序集中。</span><span class="sxs-lookup"><span data-stu-id="11da1-173">Converts text (.txt or .restext) files and XML-based resource format (.resx) files to common language runtime binary (.resources) files that can be embedded in a runtime binary executable or compiled into satellite assemblies.</span></span>  
  
 [<span data-ttu-id="11da1-174">SecAnnotate.exe（.NET 安全批注器工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-174">SecAnnotate.exe (.NET Security Annotator Tool)</span></span>](../../../docs/framework/tools/secannotate-exe-net-security-annotator-tool.md)  
 <span data-ttu-id="11da1-175">标识程序集的 SecurityCritical 和 SecuritySafeCritical 部分。</span><span class="sxs-lookup"><span data-stu-id="11da1-175">Identifies the SecurityCritical and SecuritySafeCritical portions of an assembly.</span></span> <span data-ttu-id="11da1-176">标识程序集的 `SecurityCritical` 和 `SecuritySafeCritical` 部分。</span><span class="sxs-lookup"><span data-stu-id="11da1-176">Identifies the `SecurityCritical` and `SecuritySafeCritical` portions of an assembly.</span></span>  
  
 [<span data-ttu-id="11da1-177">SignTool.exe（签名工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-177">SignTool.exe (Sign Tool)</span></span>](../../../docs/framework/tools/signtool-exe.md)  
 <span data-ttu-id="11da1-178">对文件进行数字签名，验证文件中的签名并设置文件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="11da1-178">Digitally signs files, verifies signatures in files, and time-stamps files.</span></span>  
  
 [<span data-ttu-id="11da1-179">Sn.exe（强名称工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-179">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 <span data-ttu-id="11da1-180">帮助创建带强名称的程序集。</span><span class="sxs-lookup"><span data-stu-id="11da1-180">Helps create assemblies with strong names.</span></span> <span data-ttu-id="11da1-181">此工具提供有关密钥管理、签名生成和签名验证的选项。</span><span class="sxs-lookup"><span data-stu-id="11da1-181">This tool provides options for key management, signature generation, and signature verification.</span></span>  
  
 [<span data-ttu-id="11da1-182">SOS.dll（SOS 调试扩展）</span><span class="sxs-lookup"><span data-stu-id="11da1-182">SOS.dll (SOS Debugging Extension)</span></span>](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md)  
 <span data-ttu-id="11da1-183">通过提供有关内部公共语言运行时环境的信息，帮助您在 WinDbg.exe 调试器和 Visual Studio 中调试托管程序。</span><span class="sxs-lookup"><span data-stu-id="11da1-183">Helps you debug managed programs in the WinDbg.exe debugger and in Visual Studio by providing information about the internal common language runtime environment.</span></span>  
  
 [<span data-ttu-id="11da1-184">SqlMetal.exe（代码生成工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-184">SqlMetal.exe (Code Generation Tool)</span></span>](../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 <span data-ttu-id="11da1-185">为 .NET Framework 的 LINQ to SQL 组件生成代码和映射。</span><span class="sxs-lookup"><span data-stu-id="11da1-185">Generates code and mapping for the LINQ to SQL component of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="11da1-186">Storeadm.exe（独立存储工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-186">Storeadm.exe (Isolated Storage Tool)</span></span>](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)  
 <span data-ttu-id="11da1-187">管理独立存储；提供用于列出和删除用户的存储区的选项。</span><span class="sxs-lookup"><span data-stu-id="11da1-187">Manages isolated storage; provides options for listing the user's stores and deleting them.</span></span>  
  
 [<span data-ttu-id="11da1-188">Tlbexp.exe（类型库导出程序）</span><span class="sxs-lookup"><span data-stu-id="11da1-188">Tlbexp.exe (Type Library Exporter)</span></span>](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)  
 <span data-ttu-id="11da1-189">生成一个类型库，其中描述在一个公共语言运行时程序集中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="11da1-189">Generates a type library that describes the types that are defined in a common language runtime assembly.</span></span>  
  
 [<span data-ttu-id="11da1-190">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="11da1-190">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="11da1-191">将在 COM 类型库中找到的类型定义转换为公共语言运行时程序集中的等效定义。</span><span class="sxs-lookup"><span data-stu-id="11da1-191">Converts the type definitions found in a COM type library into equivalent definitions in a common language runtime assembly.</span></span>  
  
 [<span data-ttu-id="11da1-192">Winmdexp.exe（Windows 运行时元数据导出工具）</span><span class="sxs-lookup"><span data-stu-id="11da1-192">Winmdexp.exe (Windows Runtime Metadata Export Tool)</span></span>](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)  
 <span data-ttu-id="11da1-193">将作为 .winmdobj 文件编译的 .NET Framework 程序集导出到 Windows 运行时组件，此组件打包为同时包含 Windows 运行时元数据和实现信息的 .winmd 文件。</span><span class="sxs-lookup"><span data-stu-id="11da1-193">Exports a .NET Framework assembly that is compiled as a .winmdobj file into a Windows Runtime component, which is packaged as a .winmd file that contains both Windows Runtime metadata and implementation information.</span></span>  
  
 [<span data-ttu-id="11da1-194">Winres.exe（Windows 窗体资源编辑器）</span><span class="sxs-lookup"><span data-stu-id="11da1-194">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="11da1-195">帮助您对 Windows 窗体使用的用户界面 (UI) 资源（.resx 或 .resources 文件）进行本地化。</span><span class="sxs-lookup"><span data-stu-id="11da1-195">Helps you localize user interface (UI) resources (.resx or .resources files) that are used by Windows Forms.</span></span> <span data-ttu-id="11da1-196">您可以翻译字符串，然后对控件进行大小调整、移动和隐藏操作，以使控件可以容纳本地化字符串。</span><span class="sxs-lookup"><span data-stu-id="11da1-196">You can translate strings, and then size, move, and hide controls to accommodate the localized strings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11da1-197">相关章节</span><span class="sxs-lookup"><span data-stu-id="11da1-197">Related Sections</span></span>  
 [<span data-ttu-id="11da1-198">工具</span><span class="sxs-lookup"><span data-stu-id="11da1-198">Tools</span></span>](https://msdn.microsoft.com/library/f533241c-317c-445e-88ca-c80c8d078fca)  
 <span data-ttu-id="11da1-199">包括 isXPS 合规性工具 (isXPS.exe) 和性能分析工具等工具。</span><span class="sxs-lookup"><span data-stu-id="11da1-199">Includes tools such as the isXPS Conformance tool (isXPS.exe) and performance profiling tools.</span></span>  
  
 [<span data-ttu-id="11da1-200">Windows Communication Foundation 工具</span><span class="sxs-lookup"><span data-stu-id="11da1-200">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
 <span data-ttu-id="11da1-201">包括多种工具，可使创建、部署和管理 Windows Communication Foundation (WCF) 应用程序更加容易。</span><span class="sxs-lookup"><span data-stu-id="11da1-201">Includes tools that make it easier for you to create, deploy, and manage Windows Communication Foundation (WCF) applications.</span></span>
