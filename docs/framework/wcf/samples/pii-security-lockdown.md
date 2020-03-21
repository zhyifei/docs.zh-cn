---
title: PII 安全锁定
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: ad4f4a024b04a028b815faedded58713e001cab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144261"
---
# <a name="pii-security-lockdown"></a><span data-ttu-id="a1a2f-102">PII 安全锁定</span><span class="sxs-lookup"><span data-stu-id="a1a2f-102">PII Security Lockdown</span></span>
<span data-ttu-id="a1a2f-103">此示例演示如何通过以下方式控制 Windows 通信基础 （WCF） 服务的几个与安全相关的功能：</span><span class="sxs-lookup"><span data-stu-id="a1a2f-103">This sample demonstrates how to control several security-related features of a Windows Communication Foundation (WCF) service by:</span></span>  
  
- <span data-ttu-id="a1a2f-104">加密服务配置文件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-104">Encrypting sensitive information in a service's configuration file.</span></span>  
  
- <span data-ttu-id="a1a2f-105">锁定配置文件中的元素以使嵌套的服务子目录不能重写设置。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-105">Locking elements in the configuration file so that nested service subdirectories cannot override settings.</span></span>  
  
- <span data-ttu-id="a1a2f-106">控制跟踪和消息日志中的个人身份信息 (PII) 日志记录。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-106">Controlling the logging of Personally Identifiable Information (PII) in trace and message logs.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a1a2f-107">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a1a2f-108">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a1a2f-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a1a2f-109">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a1a2f-110">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a1a2f-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a><span data-ttu-id="a1a2f-111">讨论区</span><span class="sxs-lookup"><span data-stu-id="a1a2f-111">Discussion</span></span>  
 <span data-ttu-id="a1a2f-112">这些功能中的每种功能都可以单独使用，也可以一起使用来控制服务安全的各个方面。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-112">Each of these features can be used separately or together to control aspects of a service's security.</span></span> <span data-ttu-id="a1a2f-113">这不是保护 WCF 服务的明确指南。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-113">This is not a definitive guide to securing a WCF service.</span></span>  
  
 <span data-ttu-id="a1a2f-114">.NET Framework 配置文件可以包含敏感信息，如用于连接到数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-114">The .NET Framework configuration files can contain sensitive information such as connection strings to connect to databases.</span></span> <span data-ttu-id="a1a2f-115">在 Web 承载的共享方案中，可能需要对服务配置文件中的此信息进行加密，以避免他人无意中查看配置文件中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-115">In shared, Web-hosted scenarios it may be desirable to encrypt this information in the configuration file for a service so that the data contained within the configuration file is resistant to casual viewing.</span></span> <span data-ttu-id="a1a2f-116">.NET Framework 2.0 和更高版本可以通过使用 Windows 数据保护应用程序编程接口 (DPAPI) 或 RSA 加密提供程序对配置文件的部分进行加密。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-116">.NET Framework 2.0 and later has the ability to encrypt portions of the configuration file using the Windows Data Protection application programming interface (DPAPI) or the RSA Cryptographic provider.</span></span> <span data-ttu-id="a1a2f-117">使用 DPAPI 或 RSA 的 aspnet_regiis.exe 可以对配置文件的选择部分进行加密。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-117">The aspnet_regiis.exe using the DPAPI or RSA can encrypt select portions of a configuration file.</span></span>  
  
 <span data-ttu-id="a1a2f-118">在 Web 承载的方案中，可以使服务位于其他服务的子目录中。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-118">In Web-hosted scenarios it is possible to have services in subdirectories of other services.</span></span> <span data-ttu-id="a1a2f-119">用于确定配置值的默认语义允许嵌套目录中的配置文件重写父目录中的配置值。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-119">The default semantic for determining configuration values allows configuration files in the nested directories to override the configuration values in the parent directory.</span></span> <span data-ttu-id="a1a2f-120">在某些情况下，出于各种原因可能不希望这样做。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-120">In certain situations this may be undesirable for a variety of reasons.</span></span> <span data-ttu-id="a1a2f-121">WCF 服务配置支持锁定配置值，以便在使用重写的配置值运行嵌套服务时生成异常。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-121">WCF service configuration supports the locking of configuration values so that nested configuration generates exceptions when a nested service is run using overridden configuration values.</span></span>  
  
 <span data-ttu-id="a1a2f-122">此示例演示如何在跟踪和消息日志中控制已知个人身份信息 (PII) 日志记录，如用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-122">This sample demonstrates how to control the logging of known Personally Identifiable Information (PII) in trace and message logs, such as username and password.</span></span> <span data-ttu-id="a1a2f-123">默认情况下禁用已知 PII 的日志记录，但在特定情况下，PII 日志记录可能会对应用程序的调试大有帮助。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-123">By default, logging of known PII is disabled however in certain situations logging of PII can be important in debugging an application.</span></span> <span data-ttu-id="a1a2f-124">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-124">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="a1a2f-125">此外，此示例还使用跟踪和消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-125">In addition, this sample uses tracing and message logging.</span></span> <span data-ttu-id="a1a2f-126">有关详细信息，请参阅[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)示例。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-126">For more information, see the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="encrypting-configuration-file-elements"></a><span data-ttu-id="a1a2f-127">对配置文件元素进行加密</span><span class="sxs-lookup"><span data-stu-id="a1a2f-127">Encrypting Configuration File Elements</span></span>  
 <span data-ttu-id="a1a2f-128">出于安全目的，在以 Web 为宿主的共享环境中，可能需要对包含敏感信息的特定配置元素（如数据库连接字符串）进行加密。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-128">For security purposes in a shared Web-hosting environment, it may be desirable to encrypt certain configuration elements, such as database connection strings that may contain sensitive information.</span></span> <span data-ttu-id="a1a2f-129">配置元素可以使用 .NET 框架文件夹中的 aspnet_regiis.exe 工具进行加密 例如，%WINDIR%\Microsoft.NET_Framework_v4.0.20728。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-129">A configuration element may be encrypted using the aspnet_regiis.exe tool found in the .NET Framework folder For example, %WINDIR%\Microsoft.NET\Framework\v4.0.20728.</span></span>  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a><span data-ttu-id="a1a2f-130">对示例的 Web.config 中的 appSettings 节中的值进行加密</span><span class="sxs-lookup"><span data-stu-id="a1a2f-130">To encrypt the values in the appSettings section in Web.config for the sample</span></span>  
  
1. <span data-ttu-id="a1a2f-131">使用"启动>运行"打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-131">Open a command prompt by using Start->Run….</span></span> <span data-ttu-id="a1a2f-132">键入并`cmd`单击 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-132">Type in `cmd` and click **OK**.</span></span>  
  
2. <span data-ttu-id="a1a2f-133">通过发出下面的命令导航到当前的 .NET Framework 目录：`cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-133">Navigate to the current .NET Framework directory by issuing the following command: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.</span></span>  
  
3. <span data-ttu-id="a1a2f-134">通过发出下面的命令对 Web.config 文件夹中的 appSettings 配置设置进行加密：`aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-134">Encrypt the appSettings configuration settings in the Web.config folder by issuing the following command: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.</span></span>  
  
 <span data-ttu-id="a1a2f-135">有关加密配置文件部分的详细信息，请参阅 ASP.NET 配置中的 DPAPI 操作操作（[构建安全ASP.NET应用程序：身份验证、授权和安全通信](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))）和 ASP.NET 配置中的 RSA 操作（[如何：使用 RSA ASP.NET 2.0 加密配置部分](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))）。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-135">More information about encrypting sections of configuration files can be found by reading a how-to on DPAPI in ASP.NET configuration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) and a how-to on RSA in ASP.NET configuration ([How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).</span></span>  
  
## <a name="locking-configuration-file-elements"></a><span data-ttu-id="a1a2f-136">锁定配置文件元素</span><span class="sxs-lookup"><span data-stu-id="a1a2f-136">Locking configuration file elements</span></span>  
 <span data-ttu-id="a1a2f-137">在 Web 承载的方案中，可以使服务位于其他服务的子目录中。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-137">In Web-hosted scenarios, it is possible to have services in subdirectories of services.</span></span> <span data-ttu-id="a1a2f-138">在这些情况下，通过检查 Machine.config 中的值并依次与父目录中的任何 Web.config 文件合并，然后沿目录树向下移动，最后合并包含该服务的目录中的 Web.config 文件，来计算子目录中服务的配置值。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-138">In these situations, configuration values for the service in the subdirectory are calculated by examining values in Machine.config and successively merging with any Web.config files in parent directories moving down the directory tree and finally merging the Web.config file in the directory that contains the service.</span></span> <span data-ttu-id="a1a2f-139">多数配置元素的默认行为都允许子目录中的配置文件重写父目录中设置的值。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-139">The default behavior for most configuration elements is to allow configuration files in subdirectories to override the values set in parent directories.</span></span> <span data-ttu-id="a1a2f-140">在特定情况下，可能需要阻止子目录中的配置文件重写父目录配置中设置的值。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-140">In certain situations it may be desirable to prevent configuration files in subdirectories from overriding values set in parent directory configuration.</span></span>  
  
 <span data-ttu-id="a1a2f-141">.NET Framework 提供了一种锁定配置文件元素的方式，当配置重写锁定的配置元素时会引发运行时异常。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-141">The .NET Framework provides a way to lock configuration file elements so that configurations that override locked configuration elements throw run-time exceptions.</span></span>  
  
 <span data-ttu-id="a1a2f-142">通过在配置文件中指定节点的 `lockItem` 属性，可以锁定配置元素。例如，若要锁定配置文件中的 CalculatorServiceBehavior 节点以使嵌套的配置文件中的计算器服务无法更改该行为，可以使用下面的配置。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-142">A configuration element can be locked by specifying the `lockItem` attribute for a node in the configuration file, for example, to lock the CalculatorServiceBehavior node in the configuration file so that calculator services in nested configuration files cannot change the behavior, the following configuration can be used.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>
          <serviceBehaviors>
             <behavior name="CalculatorServiceBehavior" lockItem="true">
               <serviceMetadata httpGetEnabled="True"/>
               <serviceDebug includeExceptionDetailInFaults="False" />
             </behavior>
          </serviceBehaviors>
       </behaviors>
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a1a2f-143">可以更具体地锁定配置元素。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-143">Locking of configuration elements can be more specific.</span></span> <span data-ttu-id="a1a2f-144">可以指定元素的列表作为 `lockElements` 的值以锁定子元素集合中的一组元素。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-144">A list of elements can be specified as the value to the `lockElements` to lock a set of elements within a collection of sub-elements.</span></span> <span data-ttu-id="a1a2f-145">可以指定属性的列表作为 `lockAttributes` 的值以锁定元素内的一组属性。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-145">A list of attributes can be specified as the value to the `lockAttributes` to lock a set of attributes within an element.</span></span> <span data-ttu-id="a1a2f-146">通过指定节点上的 `lockAllElementsExcept` 或 `lockAllAttributesExcept` 属性，可以锁定除指定列表外的整个元素集合或属性集合。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-146">An entire collection of elements or attributes can be locked except for a specified list by specifying the `lockAllElementsExcept` or `lockAllAttributesExcept` attributes on a node.</span></span>  
  
## <a name="pii-logging-configuration"></a><span data-ttu-id="a1a2f-147">PII 日志记录配置</span><span class="sxs-lookup"><span data-stu-id="a1a2f-147">PII Logging Configuration</span></span>  
 <span data-ttu-id="a1a2f-148">PII 日志记录由两个开关控制：Machine.config 中可以让计算机管理员允许或拒绝 PII 日志记录的计算机范围的设置，和允许应用程序管理员针对 Web.config 或 App.config 文件中的每个源来切换 PII 日志记录的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-148">Logging of PII is controlled by two switches: a computer-wide setting found in Machine.config that allows a computer administrator to permit or deny logging of PII and an application setting that allows an application administrator to toggle logging of PII for each source in a Web.config or App.config file.</span></span>  
  
 <span data-ttu-id="a1a2f-149">计算机范围的设置通过在 Machine.config `true` `false`中`machineSettings`的元素中的设置`enableLoggingKnownPii`或 控制。例如，以下允许应用程序打开 PII 的日志记录。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-149">The computer-wide setting is controlled by setting `enableLoggingKnownPii` to `true` or `false`, in the `machineSettings` element in Machine.config. For example, the following allows applications to turn on logging of PII.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="a1a2f-150">Machine.config 文件具有一个默认位置：%WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-150">The Machine.config file has a default location: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.</span></span>  
  
 <span data-ttu-id="a1a2f-151">如果 Machine.config 中没有 `enableLoggingKnownPii` 属性，则不允许使用 PII 日志记录。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-151">If the `enableLoggingKnownPii` attribute is not present in Machine.config, logging of PII is not allowed.</span></span>  
  
 <span data-ttu-id="a1a2f-152">通过在 Web.config 或 App.config 文件中将源元素的 `logKnownPii` 属性设置为 `true` 或 `false`，可以对应用程序启用 PII 日志记录。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-152">Enabling logging of PII for an application is done by setting the `logKnownPii` attribute of the source element to `true` or `false` in the Web.config or App.config file.</span></span> <span data-ttu-id="a1a2f-153">例如，下面的设置对消息日志记录和跟踪日志记录启用 PII 日志记录。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-153">For example, the following enables logging of PII for both message logging and trace logging.</span></span>  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>
                ...
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="a1a2f-154">如果未指定 `logKnownPii` 属性，则不记录 PII。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-154">If the `logKnownPii` attribute is not specified, then PII is not logged.</span></span>  
  
 <span data-ttu-id="a1a2f-155">仅当 `enableLoggingKnownPii` 设置为 `true` 且 `logKnownPii` 设置为 `true` 时才会记录 PII。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-155">PII is only logged if both `enableLoggingKnownPii` is set to `true`, and `logKnownPii` is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1a2f-156">除配置文件中列出的第一个属性外，System.Diagnostics 将忽略所有源上的所有属性。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-156">System.Diagnostics ignores all attributes on all sources except the first one listed in the configuration file.</span></span> <span data-ttu-id="a1a2f-157">向配置文件中的第二个源添加 `logKnownPii` 属性不起作用。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-157">Adding the `logKnownPii` attribute to the second source in the configuration file has no effect.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a1a2f-158">要运行此示例，需要手动修改机器。修改 Machine.config 时应小心谨慎，因为不正确的值或语法可能会阻止所有 .NET 框架应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-158">To run this sample involves manual modification of Machine.config. Care should be taken when modifying Machine.config as incorrect values or syntax may prevent all .NET Framework applications from running.</span></span>  
  
 <span data-ttu-id="a1a2f-159">使用 DPAPI 和 RSA 也可以对配置文件元素进行加密。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-159">It is also possible to encrypt configuration file elements using DPAPI and RSA.</span></span> <span data-ttu-id="a1a2f-160">有关更多信息，请参见下列链接：</span><span class="sxs-lookup"><span data-stu-id="a1a2f-160">For more information, see the following links:</span></span>  
  
- <span data-ttu-id="a1a2f-161">[生成安全的 ASP.NET 应用程序：身份验证、授权和安全通信](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="a1a2f-161">[Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))</span></span>  
  
- <span data-ttu-id="a1a2f-162">[如何：使用 RSA 加密 ASP.NET 2.0 中的配置节（可能为英文网页）](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="a1a2f-162">[How To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a1a2f-163">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="a1a2f-163">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="a1a2f-164">确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a1a2f-165">编辑 Machine.config，将 `enableLoggingKnownPii` 属性设置为 `true`，需要时添加父节点。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-165">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `true`, adding the parent nodes if necessary.</span></span>  
  
3. <span data-ttu-id="a1a2f-166">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-166">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="a1a2f-167">要在单计算机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-167">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
#### <a name="to-clean-up-the-sample"></a><span data-ttu-id="a1a2f-168">清除示例</span><span class="sxs-lookup"><span data-stu-id="a1a2f-168">To clean up the sample</span></span>  
  
1. <span data-ttu-id="a1a2f-169">编辑 Machine.config，将 `enableLoggingKnownPii` 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a1a2f-169">Edit Machine.config to set the `enableLoggingKnownPii` attribute to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a2f-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1a2f-170">See also</span></span>

- <span data-ttu-id="a1a2f-171">[AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a1a2f-171">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
