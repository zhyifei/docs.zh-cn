---
title: "Web 服务 IXmlSerializable 技术示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73ce34f101efc4f439b83e9a1ed69d286971486e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="badde-102">Web 服务 IXmlSerializable 技术示例</span><span class="sxs-lookup"><span data-stu-id="badde-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="badde-103">下载示例</span><span class="sxs-lookup"><span data-stu-id="badde-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="badde-104">此示例演示如何在 ASP.NET Web 服务中使用 <xref:System.Xml.Serialization.IXmlSerializable> 来控制自定义类型的序列化。</span><span class="sxs-lookup"><span data-stu-id="badde-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="badde-105">使用 Visual Studio 生成示例</span><span class="sxs-lookup"><span data-stu-id="badde-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="badde-106">打开 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]，然后从“文件”菜单中选择“新建网站”。</span><span class="sxs-lookup"><span data-stu-id="badde-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="badde-107">在“新建网站”对话框的左侧窗格中选择所需的编程语言，然后从右侧窗格中选择“ASP.NET Web 服务”。</span><span class="sxs-lookup"><span data-stu-id="badde-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="badde-108">键入“IXmlSerializable”作为新 Web 服务的名称。</span><span class="sxs-lookup"><span data-stu-id="badde-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="badde-109">在解决方案资源管理器窗口中，右键单击 Service.asmx 的图标，然后选择“删除”；对 Service.asmx 代码隐藏文件重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="badde-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="badde-110">右键单击该项目目录，然后选择“添加现有项”。</span><span class="sxs-lookup"><span data-stu-id="badde-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="badde-111">在对话框中，定位到语言特定的目录的 Service 子目录。</span><span class="sxs-lookup"><span data-stu-id="badde-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="badde-112">选择 Service.asmx，然后对 Service.asmx 代码隐藏文件重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="badde-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="badde-113">打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到包含上面的步骤 3 中创建的 IXmlSerializable 目录的目录。</span><span class="sxs-lookup"><span data-stu-id="badde-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="badde-114">右键单击 IXmlSerializable 目录的图标，然后选择“共享和安全”。</span><span class="sxs-lookup"><span data-stu-id="badde-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="badde-115">在“Web 共享”选项卡中，选择“共享此文件夹”，确认默认设置，包括名称 IXmlSerializable。</span><span class="sxs-lookup"><span data-stu-id="badde-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="badde-116">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="badde-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="badde-117">运行示例</span><span class="sxs-lookup"><span data-stu-id="badde-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="badde-118">打开浏览器窗口，选择其地址栏。</span><span class="sxs-lookup"><span data-stu-id="badde-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="badde-119">键入 http://localhost/IXmlSerializable/Service.asmx。</span><span class="sxs-lookup"><span data-stu-id="badde-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badde-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="badde-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
