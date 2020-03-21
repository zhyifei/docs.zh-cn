---
title: 如何：使用 MMC 卡入式查看证书
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184784"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>如何：使用 MMC 卡入式查看证书
创建安全客户端或服务时，可以使用[证书](working-with-certificates.md)作为凭据。 例如，常用类型的凭据是 X.509 证书，您可以使用 方法<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>创建该证书。

在 Windows 系统上可以使用 Microsoft 管理控制台 （MMC） 检查三种不同类型的证书存储：

- 本地计算机：存储是设备的本地存储，并且对设备上的所有用户是全局的。

- 当前用户：存储是设备上当前用户帐户的本地存储。

- 服务帐户：存储是设备上特定服务的本地存储。

## <a name="view-certificates-in-the-mmc-snap-in"></a>在 MMC 管理单元中查看证书

以下过程演示如何检查本地设备上的存储以查找适当的证书：
  
1. 选择"从**开始"** 菜单**中运行**，然后输入*mmc*。

    将显示 MMC。
  
2. 从 **"文件**"菜单中，选择 **"添加/删除对齐入"。**

    将显示 **"添加或删除对齐"** 窗口。
  
3. 从 **"可用管理单元**"列表中，选择 **"证书**"，然后选择 **"添加**"。  

    ![添加证书管理单元](./media/mmc-add-certificate-snap-in.png)
  
4. 在 **"证书入驻"** 窗口中，选择 **"计算机帐户**"，然后选择 **"下一步**"。
  
    或者，您可以选择特定服务的当前用户或服务**帐户****的"我的用户帐户**"。

    > [!NOTE]
    > 如果您不是设备的管理员，则只能管理用户帐户的证书。
  
5. 在 **"选择计算机"** 窗口中，保持**本地计算机**选中状态，然后选择 **"完成**"。  
  
6. 在 **"添加或删除对齐"** 窗口中，选择 **"确定**"。  
  
    ![添加证书管理单元](./media/mmc-certificate-snap-in-selected.png)

7. 可选：从 **"文件**"菜单中，选择 **"保存****"或"保存为"** 以保存 MMC 控制台文件以供以后使用。  

8. 要在 MMC 管理单元中查看证书，请在左侧窗格中选择 **"控制台根"，** 然后展开**证书（本地计算机）。**

    将显示每种类型的证书的目录列表。 在每个证书目录中，您可以查看、导出、导入和删除其证书。

## <a name="view-certificates-with-the-certificate-manager-tool"></a>使用证书管理器工具查看证书

您还可以使用证书管理器工具查看、导出、导入和删除证书。

### <a name="to-view-certificates-for-the-local-device"></a>查看本地设备的证书

1. 选择"**从开始"** 菜单**中运行**，然后输入*certlm.msc*。

    将显示本地设备的证书管理器工具。
  
2. 要查看证书，在左侧窗格中的 **"证书 - 本地计算机**"下，请展开要查看的证书类型的目录。

### <a name="to-view-certificates-for-the-current-user"></a>查看当前用户的证书

1. 选择"**从开始"** 菜单**中运行**，然后输入*certmgr.msc*。

    将显示当前用户的证书管理器工具。
  
2. 要查看证书，在左侧窗格中的 **"证书 - 当前用户**"下，请展开要查看的证书类型的目录。

## <a name="see-also"></a>另请参阅

- [使用证书](working-with-certificates.md)
- [如何：创建临时证书，供开发期间使用](how-to-create-temporary-certificates-for-use-during-development.md)
- [如何：检索证书的指纹](how-to-retrieve-the-thumbprint-of-a-certificate.md)
