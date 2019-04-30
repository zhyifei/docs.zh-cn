---
title: FindPrivateKey 示例-WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 72e2f49ae7c39b4a0486ec053ff1164c2d833cbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990088"
---
# <a name="findprivatekey-sample"></a>FindPrivateKey 示例

查找与证书存储区中的特定 X.509 证书关联的私钥文件的位置和名称可能很困难。 使用 FindPrivateKey.exe 工具可以更快地完成此过程。

> [!IMPORTANT]
> FindPrivateKey 是一个需要在使用之前进行编译的样本。 请参阅[构建 FindPrivateKey 项目](#to-build-the-findprivatekey-project)部分，了解如何构建 FindPrivateKey 工具的说明。

X.509 证书是由计算机管理员或计算机上的任何用户安装的。 但是，可能通过不同帐户下运行的服务访问该证书。 例如，网络服务帐户。

此帐户可能没有访问私钥文件的权限，因为证书原来并不是由它安装的。 FindPrivateKey 工具可以为您提供给定 X.509 证书的私钥文件的位置。 您可以在知道特定 X.509 证书的私钥文件的位置后立即添加或移除对此文件的权限。

使用证书来获得安全的示例使用 FindPrivateKey 工具中的*Setup.bat*文件。 一旦已找到私钥文件，您可以使用其他工具如*Cacls.exe*到该文件上设置的适当访问权限。

在运行 Windows Communication Foundation (WCF) 服务的用户帐户，如自承载的可执行文件，确保用户帐户时对文件具有只读访问权限。 运行 WCF 服务在 Internet 信息服务 (IIS) 时运行服务的默认帐户将是在 IIS 7 和早期版本中，网络服务或 IIS 7.5 和更高版本上的应用程序池标识。 有关详细信息，请参阅[应用程序池标识](/iis/manage/configuring-security/application-pool-identities)。

## <a name="examples"></a>示例

访问时为其进程没有读取的特权的证书，您将看到类似于下面的示例的异常消息：

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

此操作时，使用 FindPrivateKey 工具查找私钥文件，并将访问权限，服务下运行的进程。 例如，这可以使用的 Cacls.exe 工具如下面的示例中所示：

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>生成 FindPrivateKey 项目

若要下载项目，请访问[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://www.microsoft.com/download/details.aspx?id=21459)。

1. 打开[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]并导航到*WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS*安装示例的目录位置下的文件夹。

2. 双击 .sln 文件图标，在 Visual Studio 中打开该文件。

3. 在中**构建**菜单中，选择**重新生成解决方案**。

4. 生成解决方案将生成该文件：FindPrivateKey.exe。

## <a name="conventionscommand-line-entries"></a>约定-命令行条目

 "[*选项*]"表示一组可选的参数。

 "{*选项*}"代表一组强制参数。

 "*option1* &#124; *option2*"表示的选项集之间进行选择。

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

如果在命令提示符下不指定任何参数，则会显示此帮助文本。

## <a name="examples"></a>示例

本示例查找证书的使用者名称的文件名"CN = localhost"，当前用户的个人存储中。

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

本示例查找证书的使用者名称的文件名"CN = localhost"，在个人的当前用户存储和输出的完整目录路径。

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

此示例在“本地计算机”的“个人”存储区中查找指纹为 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" 的证书的文件名。

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
