---
title: 如何：使用 MMC 管理单元查看证书
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: d924121b9d9fa267fa7d1ada13c9dc5f5bf1523d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493345"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>如何：使用 MMC 管理单元查看证书
凭据的一种常见类型是 X.509 证书。 在创建安全服务或客户端时，可以通过使用如 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 这样的方法来指定使用证书作为客户端或服务凭据。 该方法需要多个参数，如存储证书的存储位置和搜索证书时使用的值。 下面的过程演示如何检查计算机上的存储以查找相应的证书。 查找证书指纹的示例，请参阅[如何： 检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a>在 MMC 管理单元中查看证书  
  
1.  打开一个命令提示符窗口。  
  
2.  类型`mmc`然后按 ENTER 键。 请注意，若要查看本地计算机存储中的证书，您必须具有管理员角色。  
  
3.  上**文件**菜单上，单击**添加/删除管理单元中**。  
  
4.  单击 **添加**。  
  
5.  在**添加独立管理单元中**对话框中，选择**证书**。  
  
6.  单击 **添加**。  
  
7.  在**证书管理单元**对话框中，选择**计算机帐户**单击**下一步**。 或者，您可以选择**我的用户帐户**或**服务帐户**。 如果您不是计算机的管理员，则您只能管理您的用户帐户的证书。  
  
8.  在**选择计算机**对话框中，单击**完成**。  
  
9. 在**添加独立管理单元中**对话框中，单击**关闭**。  
  
10. 上**添加/删除管理单元中**对话框中，单击**确定**。  
  
11. 在**控制台根节点**窗口中，单击**证书 （本地计算机）** 以查看证书存储的计算机。  
  
12. 可选。 若要查看您的帐户证书，请重复步骤 3 到步骤 6。 在步骤 7，而不是选择**计算机帐户**，单击**我的用户帐户**并重复执行步骤 8 到 10。  
  
13. 可选。 上**文件**菜单上，单击**保存**或**另存为**。 保存控制台文件供以后重复使用。  
  
## <a name="viewing-certificates-with-internet-explorer"></a>使用 Internet Explorer 查看证书  
 您也可以通过使用 Internet Explorer 来查看、导出、导入和删除证书。  
  
#### <a name="to-view-certificates-with-internet-explorer"></a>使用 Internet Explorer 查看证书  
  
1.  在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**以显示**Internet 选项**对话框。  
  
2.  单击**内容**选项卡。  
  
3.  下**证书**，单击**证书**。  
  
4.  若要查看的任何证书的详细信息，选择的证书，单击**视图**。  
  
## <a name="see-also"></a>请参阅  
 [使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [如何：创建开发期间使用的临时证书](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
