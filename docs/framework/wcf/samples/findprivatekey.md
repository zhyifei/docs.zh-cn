---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1ff00bead6130601070ac94686ee9622a6fe218
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="findprivatekey"></a>FindPrivateKey
查找与证书存储区中的特定 X.509 证书关联的私钥文件的位置和名称可能很困难。 使用 FindPrivateKey.exe 工具可以更快地完成此过程。  
  
> [!IMPORTANT]
>  FindPrivateKey 是一个需要在使用之前进行编译的样本。 有关如何构建 FindPrivateKey 工具，请参阅"以生成 FindPrivateKey 项目"下面的部分的说明。  
  
 X.509 证书是由计算机管理员或计算机上的任何用户安装的。 但是，该证书可以由使用其他帐户（例如 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 上的 ASPNET 或 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 上的 NETWORK SERVICE 帐户）运行的服务来访问。  
  
 此帐户可能没有访问私钥文件的权限，因为证书原来并不是由它安装的。 FindPrivateKey 工具可以为您提供给定 X.509 证书的私钥文件的位置。 您可以在知道特定 X.509 证书的私钥文件的位置后立即添加或移除对此文件的权限。  
  
 使用证书确保安全性的示例在 Setup.bat 文件中使用 FindPrivateKey 工具。 找到私钥文件后，您可以使用其他工具（如 Cacls.exe）设置该文件的适当访问权限。  
  
 使用用户帐户（如自承载可执行文件）运行 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务时，请确保该用户帐户具有该文件的只读访问权限。 使用 Internet 信息服务 (IIS) 运行 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时，该服务使用的默认帐户是 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 上的 ASPNET 或 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 上的 NETWORK SERVICE，该帐户默认情况下没有私钥文件的访问权限。  
  
## <a name="examples"></a>示例  
 访问进程没有读取特权的证书时，您将看到类似如下示例的异常消息。  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 发生这种情况时，可以使用 FindPrivateKey 工具查找私钥文件，然后为服务正在其中运行的进程设置访问权限。 例如，可以使用下面示例中所示的 Cacls.exe 工具完成此操作。  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a>生成 FindPrivateKey 项目  
  
1.  打开 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，然后导航到安装此示例的目录位置下语言特定的子目录。  
  
2.  双击 .sln 文件图标，在 Visual Studio 中打开该文件。  
  
3.  在**生成**菜单上，选择**重新生成解决方案**。 客户端程序文件在 client\bin 中生成，服务程序文件在 service\bin 中生成。  
  
4.  生成解决方案将生成如下文件：FindPrivateKey.exe。  
  
## <a name="conventionscommand-line-entries"></a>约定 - 命令行条目  
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
  
 如果没在命令提示符中指定任何参数，将显示此帮助文本。  
  
## <a name="examples"></a>示例  
 此示例在 Current User.FindPrivateKey My CurrentUser -n "CN=localhost" 的“个人”存储区中查找主题名称为 "CN=localhost" 的证书的文件名。  
  
 此示例在 Current 的“个人”存储区中查找主题名称为 "CN=localhost" 的证书的文件名，并输出完整的目录路径。  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 此示例在“本地计算机”的“个人”存储区中查找指纹为 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" 的证书的文件名。  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a>另请参阅
