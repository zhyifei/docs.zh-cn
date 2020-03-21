---
title: 使用 WCF 开发工具
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183080"
---
# <a name="using-the-wcf-development-tools"></a>使用 WCF 开发工具
本节介绍可视化工作室开发工具，这些工具可帮助您开发 WCF 服务。  
  
 您可以使用 Visual Studio 模板作为基础来快速构建您自己的服务，然后使用 WCF 服务自动主机和 WCF 测试客户端来调试和测试服务。 通过一起使用这些工具，可以快速完美地完成调试和测试过程，无需在早期阶段提交给承载模型。  

 > [!NOTE]
 > 从 Visual Studio 2017 开始，默认情况下不会安装 WCF 开发工具。 为了使用这些功能，必须确保在可视化工作室安装程序中选择 Windows 通信基础组件。
  
## <a name="the-wcf-developer-tools"></a>WCF 开发人员工具  
 [WCF Visual Studio 模板](wcf-vs-templates.md)  
  
 您可以使用 Visual Studio 中预定义的 Visual Studio 项目和项目模板来快速构建 WCF 服务和周围应用程序。  
  
 [WCF 服务主机 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 WCF 服务自动主机 （WcfSvcHost.exe） 允许您启动 Visual Studio 调试器 （F5） 以自动托管和测试您已实现的服务。 然后，您可以使用 WCF 测试客户端 （wcfTestClient.exe） 或您自己的客户端测试服务，以查找和修复任何潜在错误。  
  
 [WCF 测试客户端 (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 WCF 测试客户端 （WcfTestClient.exe） 是一个 GUI 工具，允许您输入任意类型的参数，将该输入提交到服务，并查看服务发送回的响应。 与 WCF 服务自动主机结合使用时，可提供无缝的服务测试体验。  
  
 [从 XML 生成数据类型类](generating-data-type-classes-from-xml.md)  
  
 可将存储在剪贴板中的 XML 数据粘贴到代码页中。 数据中定义的类将被转换为代码类型。  
  
## <a name="using-the-tools-without-administrator-privilege"></a>在无管理员权限的情况下使用工具  
 为了使没有管理员权限的用户能够开发 WCF 服务，在安装 Visual Studio 期间为命名空间"http://+:8731/Design_Time_Addresses创建 ACL（访问控制列表）。 该 ACL 被设置为“(UI)”，这将包括登录到此计算机的所有交互用户。 管理员可以在此 ACL 中添加或移除用户，或者打开其他端口。此 ACL 支持 WCF 或 WF 模板以其各自的默认配置发送和接收数据。 它还允许用户使用 WCF 服务自动主机 （wcfSvcHost.exe），而无需授予管理员权限。  
  
 您可以使用 Windows Vista 中的 Netsh.exe 工具在提升的管理员帐户下修改访问权限。 下面是使用 Netsh.exe 的示例。  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 有关 Netsh.exe 的详细信息，请参阅[如何使用 Netsh.exe 工具和命令行开关](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))。  
  
## <a name="see-also"></a>另请参阅

- [WCF Visual Studio 模板](wcf-vs-templates.md)
- [WCF 服务主机 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF 测试客户端 (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
