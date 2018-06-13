---
title: Web 服务 IXmlSerializable 技术示例
ms.date: 03/30/2017
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
ms.openlocfilehash: eb117f720e7541ac6460b5adfd0eecc7901f4fdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582709"
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="e7e16-102">Web 服务 IXmlSerializable 技术示例</span><span class="sxs-lookup"><span data-stu-id="e7e16-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="e7e16-103">下载示例</span><span class="sxs-lookup"><span data-stu-id="e7e16-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="e7e16-104">此示例演示如何在 ASP.NET Web 服务中使用 <xref:System.Xml.Serialization.IXmlSerializable> 来控制自定义类型的序列化。</span><span class="sxs-lookup"><span data-stu-id="e7e16-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="e7e16-105">使用 Visual Studio 生成示例</span><span class="sxs-lookup"><span data-stu-id="e7e16-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="e7e16-106">打开 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]，然后从“文件”菜单中选择“新建网站”。</span><span class="sxs-lookup"><span data-stu-id="e7e16-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="e7e16-107">在“新建网站”对话框的左侧窗格中选择所需的编程语言，然后从右侧窗格中选择“ASP.NET Web 服务”。</span><span class="sxs-lookup"><span data-stu-id="e7e16-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="e7e16-108">键入“IXmlSerializable”作为新 Web 服务的名称。</span><span class="sxs-lookup"><span data-stu-id="e7e16-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="e7e16-109">在解决方案资源管理器窗口中，右键单击 Service.asmx 的图标，然后选择“删除”；对 Service.asmx 代码隐藏文件重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="e7e16-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="e7e16-110">右键单击该项目目录，然后选择“添加现有项”。</span><span class="sxs-lookup"><span data-stu-id="e7e16-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="e7e16-111">在对话框中，定位到语言特定的目录的 Service 子目录。</span><span class="sxs-lookup"><span data-stu-id="e7e16-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="e7e16-112">选择 Service.asmx，然后对 Service.asmx 代码隐藏文件重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="e7e16-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="e7e16-113">打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到包含上面的步骤 3 中创建的 IXmlSerializable 目录的目录。</span><span class="sxs-lookup"><span data-stu-id="e7e16-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="e7e16-114">右键单击 IXmlSerializable 目录的图标，然后选择“共享和安全”。</span><span class="sxs-lookup"><span data-stu-id="e7e16-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="e7e16-115">在“Web 共享”选项卡中，选择“共享此文件夹”，确认默认设置，包括名称 IXmlSerializable。</span><span class="sxs-lookup"><span data-stu-id="e7e16-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="e7e16-116">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e7e16-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="e7e16-117">运行示例</span><span class="sxs-lookup"><span data-stu-id="e7e16-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="e7e16-118">打开浏览器窗口，选择其地址栏。</span><span class="sxs-lookup"><span data-stu-id="e7e16-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="e7e16-119">类型**http://localhost/IXmlSerializable/Service.asmx**。</span><span class="sxs-lookup"><span data-stu-id="e7e16-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e16-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7e16-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
