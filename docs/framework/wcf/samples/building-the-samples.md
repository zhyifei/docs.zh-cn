---
title: 生成 Windows Communication Foundation 示例
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 637b862d81ce4eeddc56acb24a527e6937f33f64
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="building-the-windows-communication-foundation-samples"></a>生成 Windows Communication Foundation 示例
使用 Visual Studio 2010 或使用可以生成 Windows Communication Foundation (WCF) 示例**msbuild**命令从命令行。 本主题介绍这两个过程。  
  
> [!NOTE]
>  在生成或运行任何 WCF 示例之前, 确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
### <a name="to-build-the-sample-using-a-command-prompt"></a>使用命令提示生成示例  
  
1.  使用管理员特权打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示，然后定位到安装示例的目录位置下的语言特定的子目录。  
  
2.  类型`msbuild`在命令行。 客户端程序文件在 client\bin 中生成，服务程序文件在 service\bin 中生成。 如果服务由 Internet Information Services (IIS) 承载，服务程序文件还将被复制到 servicemodelsamples 目录及其 \bin 子目录中。  
  
> [!NOTE]
>  您必须在 %systemdrive%\inetpub\wwwroot 上设置 ACL，以便为您运行的帐户授予修改权限。 否则，某些后期生成事件将失败。 或者，您可以将 ACL 保留原样，而以管理员身份运行 SDK 命令提示。  
  
### <a name="to-build-the-sample-using-visual-studio"></a>使用 Visual Studio 生成示例  
  
1.  如果你使用[!INCLUDE[wv](../../../../includes/wv-md.md)]， [!INCLUDE[lserver](../../../../includes/lserver-md.md)]，Windows 7 或 Windows Server 2008 R2，并运行[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]，必须用提升的权限运行 Visual Studio。 为此，请右键单击开始菜单上的图标，然后单击**以管理员身份运行**。  
  
2.  从**文件**菜单在 Visual Studio 中，单击**打开**，然后单击**项目/解决方案**。 导航到在其中安装此示例中，目录下的特定于语言的子目录，并双击.sln 文件图标，以在 Visual Studio 中打开解决方案。  
  
3.  在**生成**菜单上，选择**重新生成解决方案**。 客户端程序文件在 client\bin 中生成，服务程序文件在 service\bin 中生成。 如果服务在 IIS 中承载，服务程序文件还将被复制到 servicemodelsamples 目录及其 \bin 子目录中。  
  
> [!NOTE]
>  您必须在 %systemdrive%\inetpub\wwwroot 上设置 ACL，以便为您运行的帐户授予修改权限。 否则，某些后期生成事件将失败。 或者，您可以将 ACL 保留原样，而以管理员身份运行 SDK 命令提示或 Visual Studio。 某些 Visual Studio 操作（例如，为 ASP.Net 工作进程附加调试器）也需要管理特权。  
  
## <a name="setup-batch-files-and-scripts"></a>设置批处理文件和脚本  
 Setup.exe 和 Cleanup.exe 批处理文件和脚本应在 Visual Studio 命令提示中运行。 有几个设置和清理文件将执行需要具有管理特权的任务，应使用管理特权来启动它们。  
  
## <a name="important-security-information-about-metadata-endpoints"></a>有关元数据终结点的重要安全信息  
 为了防止无意中泄露潜在的敏感服务元数据，Windows Communication Foundation (WCF) 服务的默认配置，请禁用元数据发布。 默认情况下此行为是安全的，但也意味着你无法使用元数据导入工具（例如 Svcutil.exe）生成调用服务所需的客户端代码，除非在配置中显式启用服务的元数据发布行为。 为了使示例体验更简单，几乎所有示例都公开一个不安全的元数据发布终结点。 此类终结点或许可以供未通过身份验证的匿名使用者使用，因此在部署此类终结点之前，必须谨慎以确保适合公开透露服务元数据。 有关发布服务元数据的详细信息，请参阅[元数据发布行为](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)示例。 请参阅[自定义安全元数据终结点](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)示例有关保护元数据终结点的示例。  
  
## <a name="exception-handling"></a>异常处理  
 一般来说，这些示例不包括异常处理，以使代码集中处理示例的主题。 有关异常处理的详细信息，请参阅[预期异常](../../../../docs/framework/wcf/samples/expected-exceptions.md)示例。  
  
## <a name="regenerating-clients-and-configuration-with-svcutil"></a>使用 Svcutil 重新生成客户端和配置  
 你可以使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)重新生成的大多数示例用于客户端代码和配置。 某些示例需要手动编辑的配置。 例如，如果您使用 Svcutil.exe 为某个使用客户端证书凭据的示例重新生成配置，必须手动指定之前配置的凭据。 某些示例使用特定的 Svcutil.exe 选项来影响生成的代码，这些选项在具体的示例主题中进行指定。  
  
#### <a name="to-regenerate-the-client-and-configuration-files"></a>重新生成客户端和配置文件  
  
1.  打开 SDK 命令提示，然后定位到安装示例的目录位置下的语言特定的子目录。  
  
2.  如果服务是 Web 承载的类型，请使用以下命令。  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     如果服务是自承载类型，请键入以下命令。  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     替换http://localhost:8000/ServiceModelSamples/service.svc/mex与自承载的服务的 mex 终结点的地址。  
  
     若要在 Visual Basic 类型中生成客户端，请使用以下命令。  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
     如果服务是自承载类型，请使用以下命令。  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
    > [!NOTE]
    >  若要跳过生成的客户端配置将添加 **/noConfig**选项。  
  
## <a name="see-also"></a>请参阅  
 [运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)  
 [ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
