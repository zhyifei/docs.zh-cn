---
title: "FindPrivateKey 示例-WCF"
ms.date: 12/04/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32e1a4a3de01371d67be8d19613b1f29c1ce3c29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="findprivatekey-sample"></a>FindPrivateKey 示例

查找与证书存储区中的特定 X.509 证书关联的私钥文件的位置和名称可能很困难。 使用 FindPrivateKey.exe 工具可以更快地完成此过程。

> [!IMPORTANT]
> FindPrivateKey 是一个需要在使用之前进行编译的样本。 请参阅[以生成 FindPrivateKey 项目](#to-build-the-findprivatekey-project)一部分以获取有关如何构建 FindPrivateKey 工具的说明。

X.509 证书是由计算机管理员或计算机上的任何用户安装的。 但是，该证书可能在不同帐户下运行的服务可访问。 例如，NETWORK SERVICE 帐户。

此帐户可能没有访问私钥文件的权限，因为证书原来并不是由它安装的。 FindPrivateKey 工具可以为您提供给定 X.509 证书的私钥文件的位置。 您可以在知道特定 X.509 证书的私钥文件的位置后立即添加或移除对此文件的权限。

使用证书来获得安全的示例使用中的 FindPrivateKey 工具*Setup.bat*文件。 找到私钥文件后你可以使用其他工具如*Cacls.exe*设置文件的适当访问权限。

在运行 Windows Communication Foundation (WCF) 服务的用户帐户，如自承载的可执行文件，确保用户帐户时请对文件具有只读访问权限。 运行 WCF 服务在 Internet 信息服务 (IIS) 时运行该服务的默认帐户将是网络服务在 IIS 7 和早期版本中或在 IIS 7.5 和更高版本上的应用程序池标识。 有关详细信息，请参阅[应用程序池标识](/iis/manage/configuring-security/application-pool-identities)。

## <a name="examples"></a>示例

访问时为其进程不具有读取的权限的证书，你将看到类似于下面的示例的异常消息：

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

当发生这种情况时，使用 FindPrivateKey 工具查找私钥文件，并将访问权限的进程的服务下运行。 例如，这可以通过实现的 Cacls.exe 工具中下面的示例所示：

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>生成 FindPrivateKey 项目

若要下载的项目，请访问[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://www.microsoft.com/download/details.aspx?id=21459)。

1. 打开[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]并导航到*WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS*安装示例的位置的目录位置下的文件夹。

2. 双击 .sln 文件图标，在 Visual Studio 中打开该文件。

3. 在**生成**菜单上，选择**重新生成解决方案**。

4. 生成解决方案将生成如下文件：FindPrivateKey.exe。

## <a name="conventionscommand-line-entries"></a>约定-命令行条目

 "[*选项*]"表示一组可选的参数。

 "{*选项*}"代表一组强制参数。

 "*选项 1* &#124;*选项 2*"代表一种选择的选项集之间。

 "\<*值*>"代表要输入的参数值。

## <a name="usage"></a>用法

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

其中：

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

如果未指定参数在命令提示符下，将显示此帮助文本。

## <a name="examples"></a>示例

本示例查找的文件名的证书的主题名称为"CN = localhost"，当前用户的个人存储中。

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

本示例查找的文件名的证书的主题名称为"CN = localhost"，在个人存储当前用户的并输出完整的目录路径。

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

此示例在“本地计算机”的“个人”存储区中查找指纹为 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" 的证书的文件名。

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
