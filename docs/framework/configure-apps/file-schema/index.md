---
title: .NET Framework 的配置文件架构
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c7aebbfd0d25f6c5a9266857816a1723cb0c660e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466579"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="d4fb3-102">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d4fb3-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="d4fb3-103">配置文件是可用来更改应用设置并为其设置策略的标准 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="d4fb3-104">.NET Framework 配置架构由一些可在配置文件中用来控制应用行为的元素组成。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="d4fb3-105">本节的目录反映了架构的层次结构：启动、运行时、网络和其他配置设置类型。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="d4fb3-106">有关配置文件类型、格式和位置的信息，请参阅[配置应用](~/docs/framework/configure-apps/index.md)一文。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](~/docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="d4fb3-107">若要直接编辑配置文件，需要自行熟悉 XML。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4fb3-108">配置文件中的 XML 标记和特性区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d4fb3-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="d4fb3-109">In this section</span></span>

<span data-ttu-id="d4fb3-110">[**\<configuration>** 元素](~/docs/framework/configure-apps/file-schema/configuration-element.md)描述 `<configuration>` 元素，它是所有配置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-110">[**\<configuration>** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="d4fb3-111">[**\<assemblyBinding>** 元素](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-111">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="d4fb3-112">[**\<linkedConfiguration>** 元素](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-112">[**\<linkedConfiguration>** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="d4fb3-113">[启动设置架构](~/docs/framework/configure-apps/file-schema/startup/index.md)描述指定要使用的公共语言运行时版本的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-113">[Startup Settings Schema](~/docs/framework/configure-apps/file-schema/startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="d4fb3-114">[运行时设置架构](~/docs/framework/configure-apps/file-schema/runtime/index.md)描述配置程序集绑定和运行时行为的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-114">[Runtime Settings Schema](~/docs/framework/configure-apps/file-schema/runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="d4fb3-115">[网络设置架构](~/docs/framework/configure-apps/file-schema/network/index.md)描述指定 .NET Framework 如何连接到 Internet 的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-115">[Network Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="d4fb3-116">[加密设置架构](~/docs/framework/configure-apps/file-schema/cryptography/index.md)描述将友好算法名映射到实现密码算法的类的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-116">[Cryptography Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="d4fb3-117">[配置设置架构](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md)描述用于创建和使用自定义设置的配置节的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-117">[Configuration Sections Schema](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="d4fb3-118">[跟踪和调试设置架构](~/docs/framework/configure-apps/file-schema/trace-debug/index.md)描述指定跟踪开关和侦听器的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-118">[Trace and Debug Settings Schema](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="d4fb3-119">[编译器和语言提供程序设置架构](~/docs/framework/configure-apps/file-schema/compiler/index.md)描述指定可用语言提供程序的编译器配置的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-119">[Compiler and Language Provider Settings Schema](~/docs/framework/configure-apps/file-schema/compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="d4fb3-120">[应用程序设置架构](~/docs/framework/configure-apps/file-schema/application-settings-schema.md)描述允许 Windows 窗体或 ASP.NET 应用程序存储和检索应用程序范围设置和用户范围设置的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-120">[Application Settings Schema](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="d4fb3-121">[应用设置架构](~/docs/framework/configure-apps/file-schema/appsettings/index.md)包含自定义应用程序设置，如文件路径、XML Web service URL 或应用程序的任何其他自定义配置信息。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-121">[App Settings Schema](~/docs/framework/configure-apps/file-schema/appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="d4fb3-122">[Web 设置架构](~/docs/framework/configure-apps/file-schema/web/index.md) Web 设置架构中的所有元素，包括用于配置 ASP.NET 如何与主机应用程序（如 IIS）一起工作的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-122">[Web Settings Schema](~/docs/framework/configure-apps/file-schema/web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="d4fb3-123">在 Aspnet.config 文件中使用。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="d4fb3-124">[Windows 窗体配置架构](winforms/index.md) Windows 窗体应用程序配置节中的所有元素，包括多监视器和高 DPI 支持等自定义。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="d4fb3-125">[WCF 配置架构](~/docs/framework/configure-apps/file-schema/wcf/index.md)用于配置 WCF 服务和客户端应用程序的所有元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-125">[WCF Configuration Schema](~/docs/framework/configure-apps/file-schema/wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="d4fb3-126">[WCF 指令语法](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md)描述用于定义 .svc 编译器使用的特定于页的属性的 `@ServiceHost` 指令。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-126">[WCF Directive Syntax](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="d4fb3-127">[WIF 配置架构](windows-identity-foundation/index.md) Windows Identity Foundation (WIF) 配置架构的所有元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d4fb3-128">相关章节</span><span class="sxs-lookup"><span data-stu-id="d4fb3-128">Related sections</span></span>

<span data-ttu-id="d4fb3-129">[远程处理设置架构](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)描述对实现远程处理的客户端和服务器应用程序进行配置的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-129">[Remoting Settings Schema](https://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="d4fb3-130">[ASP.NET 设置架构](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx)描述控制 ASP.NET Web 应用程序的行为的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-130">[ASP.NET Settings Schema](https://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="d4fb3-131">[Web 服务设置架构](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e)描述控制 ASP.NET Web 服务及其客户端的行为的元素。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-131">[Web Services Settings Schema](https://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="d4fb3-132">[配置 .NET Framework 应用](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)描述如何在 .NET Framework 中配置安全性、程序集绑定和远程处理。</span><span class="sxs-lookup"><span data-stu-id="d4fb3-132">[Configuring .NET Framework Apps](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
