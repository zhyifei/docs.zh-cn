---
title: "Web 服务泛型序列化技术示例 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Web 服务泛型序列化技术示例
[下载示例](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 此示例演示如何在 ASP.NET Web 服务中使用和控制泛型的序列化。  
  
### 使用 Visual Studio 生成示例  
  
1.  打开 Visual Studio，然后从**“文件”**菜单中选择**“新建网站”**。  
  
2.  在**“新建网站”**对话框的左侧窗格中选择所需的编程语言，然后从右侧窗格中选择**“ASP.NET Web 服务”**。  
  
3.  单击**“浏览”**，然后定位到 \\CS\\GenericsService 子目录。  
  
4.  选择 Service.asmx 以在 Visual Studio 中打开该文件。  
  
5.  在**“生成”**菜单上，单击**“生成解决方案”**。  
  
> [!NOTE]
>  此列表中的前五个步骤是可选的。.NET Framework 运行时将在首次请求该 Web 服务时自动生成该服务。  
  
> [!NOTE]
>  必须执行以下步骤，才能生成示例。  
  
1.  打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到 \\CS 子目录。  
  
2.  右击 GenericsService 子目录的图标，然后选择**“共享和安全”**。  
  
3.  在**“Web 共享”**选项卡中，选择**“共享此文件夹”**。  
  
> [!IMPORTANT]
>  请记下**“别名”**窗格中列出的虚拟目录名，因为您需要用它来运行示例。  
  
### 使用 Internet 信息服务生成示例  
  
1.  打开**“Internet 信息服务”**管理单元，然后展开**“网站”**。  
  
2.  左击**“默认网站”**，选择**“新建”**，然后选择**“虚拟目录?”**来创建**“虚拟目录创建向导”**。  
  
3.  单击**“下一步”**，输入虚拟目录的公共别名，然后再单击**“下一步”**。  
  
4.  输入保存示例的目录路径（通常是 \\CS\\GenericsService 子目录），然后单击**“下一步”**。单击**“下一步”**完成向导。  
  
> [!IMPORTANT]
>  请记下**“别名”**窗格中列出的虚拟目录名，因为您需要用它来运行示例。  
  
### 运行示例  
  
1.  打开浏览器窗口，选择其地址栏。  
  
2.  键入 **http:\/\/localhost\/**\[虚拟目录\]**\/Service.asmx**，其中“\[虚拟目录\]”表示在您生成该示例时创建的虚拟目录。  
  
## 备注  
 该示例将显示默认的 ASP.NET 页面，该页面包含指向 Web 服务定义的链接。除了修改 Web 服务的源代码以外，还可以自定义其显示方式。有关更多信息，请参见[Building XML Web Service Clients](http://msdn.microsoft.com/zh-cn/c606f3cb-4111-45b4-ae42-9300420fa16c)。  
  
## 请参阅  
 <xref:System.Collections.Generic>   
 <xref:System.Web.Services>   
 <xref:System.Xml.Serialization>   
 [序列化](../../../docs/framework/serialization/index.md)   
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/zh-cn/1e64af78-d705-4384-b08d-591a45f4379c)