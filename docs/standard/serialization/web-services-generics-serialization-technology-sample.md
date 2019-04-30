---
title: Web 服务泛型序列化技术示例
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 6549dc1c3d428a5fb74fe0212549ef3f3f6510d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018042"
---
# <a name="web-services-generics-serialization-technology-sample"></a><span data-ttu-id="fa0b7-102">Web 服务泛型序列化技术示例</span><span class="sxs-lookup"><span data-stu-id="fa0b7-102">Web Services Generics Serialization Technology Sample</span></span>
[<span data-ttu-id="fa0b7-103">下载示例</span><span class="sxs-lookup"><span data-stu-id="fa0b7-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 <span data-ttu-id="fa0b7-104">此示例演示如何在 ASP.NET Web 服务中使用和控制泛型的序列化。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-104">This sample shows how to use and control the serialization of generics in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="fa0b7-105">使用 Visual Studio 生成示例</span><span class="sxs-lookup"><span data-stu-id="fa0b7-105">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="fa0b7-106">打开 Visual Studio，然后从“文件”菜单中选择“新建网站”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-106">Open Visual Studio and select **New Web Site** from the **File** menu.</span></span>  
  
2. <span data-ttu-id="fa0b7-107">在“新建网站”对话框的左侧窗格中选择所需的编程语言，然后从右侧窗格中选择“ASP.NET Web 服务”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-107">In the **New Web Site** dialog, select from the left pane your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3. <span data-ttu-id="fa0b7-108">单击“浏览”，然后导航至 \CS\GenericsService 子目录。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-108">Click **Browse** and navigate to the \CS\GenericsService subdirectory.</span></span>  
  
4. <span data-ttu-id="fa0b7-109">选择 Service.asmx 以在 Visual Studio 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-109">Select Service.asmx to open the file in Visual Studio.</span></span>  
  
5. <span data-ttu-id="fa0b7-110">在 **“生成”** 菜单上，单击 **“生成解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-110">On the **Build** menu, click **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa0b7-111">此列表中的前五个步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-111">The first five steps in this list are optional.</span></span> <span data-ttu-id="fa0b7-112">.NET Framework 运行时将在首次请求该 Web 服务时自动生成该服务。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-112">The .NET Framework runtime will automatically generate the Web service the first time the service is requested.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa0b7-113">必须执行以下步骤，才能生成示例。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-113">The following steps are required to build the sample.</span></span>  
  
1. <span data-ttu-id="fa0b7-114">打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]并导航到 \CS 子目录。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-114">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the \CS subdirectory.</span></span>  
  
2. <span data-ttu-id="fa0b7-115">右键单击 GenericsService 子目录的图标，然后选择“共享和安全”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-115">Right-click the icon for the GenericsService subdirectory, and select **Sharing and Security**.</span></span>  
  
3. <span data-ttu-id="fa0b7-116">在“Web 共享”选项卡中，选择“共享此文件夹”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-116">In the **Web Sharing** tab, select **Share this Folder**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa0b7-117">请记下“别名”窗格中列出的虚拟目录名，因为需要用它来运行示例。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-117">Take note of the virtual directory name that is listed in the **Aliases** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-build-the-sample-using-internet-information-services"></a><span data-ttu-id="fa0b7-118">使用 Internet 信息服务生成示例</span><span class="sxs-lookup"><span data-stu-id="fa0b7-118">To build the sample using Internet Information Services</span></span>  
  
1. <span data-ttu-id="fa0b7-119">打开“Internet Information Services”管理单元，然后展开“网站”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-119">Open the **Internet Information Services** management snap-in and expand **Web Sites**.</span></span>  
  
2. <span data-ttu-id="fa0b7-120">左键单击“默认网站”，选择“新建”，然后选择“虚拟目录?”来创建“虚拟目录创建向导”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-120">Left-click **Default Web Site**, select **New**, and then select **Virtual Directory?** to create the **Virtual Directory Creation Wizard**.</span></span>  
  
3. <span data-ttu-id="fa0b7-121">单击“下一步”，输入虚拟目录的公共别名，然后再单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-121">Click **Next**, enter the public alias for your virtual directory, and click **Next**.</span></span>  
  
4. <span data-ttu-id="fa0b7-122">输入保存示例的目录路径（通常是 \CS\GenericsService 子目录），然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-122">Enter the path to the directory where you saved the sample (normally the \CS\GenericsService subdirectory) and click **Next**.</span></span> <span data-ttu-id="fa0b7-123">单击“下一步”完成向导。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-123">Click **Next** to finish the wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa0b7-124">请记下“别名”窗格中列出的虚拟目录名，因为需要用它来运行示例。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-124">Take note of the virtual directory name that is listed in the **Alias** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="fa0b7-125">运行示例</span><span class="sxs-lookup"><span data-stu-id="fa0b7-125">To run the sample</span></span>  
  
1. <span data-ttu-id="fa0b7-126">打开浏览器窗口，选择其地址栏。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-126">Open a browser window and select its address bar.</span></span>  
  
2. <span data-ttu-id="fa0b7-127">类型`http://localhost/[virtual directory]/Service.asmx`，其中`[virtual directory]`表示生成该示例时创建的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-127">Type `http://localhost/[virtual directory]/Service.asmx`, where `[virtual directory]` represents the virtual directory you created when you built the sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa0b7-128">备注</span><span class="sxs-lookup"><span data-stu-id="fa0b7-128">Remarks</span></span>  
 <span data-ttu-id="fa0b7-129">该示例将显示默认的 ASP.NET 页面，该页面包含指向 Web 服务定义的链接。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-129">The sample displays a default ASP.NET page that contains links to the definition of the Web Service.</span></span> <span data-ttu-id="fa0b7-130">除了修改 Web 服务的源代码以外，还可以自定义其显示方式。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-130">You can customize the display in addition to modifying the source code for the Web service.</span></span> <span data-ttu-id="fa0b7-131">有关详细信息，请参阅[生成 XML Web services 客户端](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="fa0b7-131">For more information, see [Building XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0b7-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa0b7-132">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Web.Services>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="fa0b7-133">序列化</span><span class="sxs-lookup"><span data-stu-id="fa0b7-133">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- <span data-ttu-id="fa0b7-134">[使用 ASP.NET 创建的 XML Web service 以及 XML Web Service 客户端](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fa0b7-134">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
