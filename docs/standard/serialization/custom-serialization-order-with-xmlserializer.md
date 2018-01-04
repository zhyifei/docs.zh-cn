---
title: "使用 XmlSerializer 自定义序列化顺序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae5969060938763fee63c514de0a87eadbe6537a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="892fc-102">使用 XmlSerializer 自定义序列化顺序</span><span class="sxs-lookup"><span data-stu-id="892fc-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="892fc-103">下载示例</span><span class="sxs-lookup"><span data-stu-id="892fc-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="892fc-104">此示例演示如何控制序列化和反序列化元素的顺序来进行 XML 序列化。</span><span class="sxs-lookup"><span data-stu-id="892fc-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="892fc-105">有关序列化的更多信息，请查看源代码中的注释以及 build.proj 文件。</span><span class="sxs-lookup"><span data-stu-id="892fc-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="892fc-106">使用命令提示生成示例</span><span class="sxs-lookup"><span data-stu-id="892fc-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="892fc-107">打开命令提示窗口，然后定位到该示例的语言特定子目录之一。</span><span class="sxs-lookup"><span data-stu-id="892fc-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="892fc-108">在命令行中键入 msbuild CustomOrder.sln。</span><span class="sxs-lookup"><span data-stu-id="892fc-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="892fc-109">使用 Visual Studio 生成示例</span><span class="sxs-lookup"><span data-stu-id="892fc-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="892fc-110">打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到该示例的特定语言的子目录。</span><span class="sxs-lookup"><span data-stu-id="892fc-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="892fc-111">双击 CustomOrder.sln 的图标，在 Visual Studio 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="892fc-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="892fc-112">在“生成”菜单中选择“生成解决方案”。</span><span class="sxs-lookup"><span data-stu-id="892fc-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="892fc-113">示例应用程序将在默认的 \bin 或 \bin\Debug 子目录中生成。</span><span class="sxs-lookup"><span data-stu-id="892fc-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="892fc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="892fc-114">See Also</span></span>  
 [<span data-ttu-id="892fc-115">基本序列化</span><span class="sxs-lookup"><span data-stu-id="892fc-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="892fc-116">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="892fc-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="892fc-117">使用属性控制 XML 序列化</span><span class="sxs-lookup"><span data-stu-id="892fc-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="892fc-118">XML 序列化简介</span><span class="sxs-lookup"><span data-stu-id="892fc-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="892fc-119">序列化</span><span class="sxs-lookup"><span data-stu-id="892fc-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="892fc-120">XML 和 SOAP 序列化</span><span class="sxs-lookup"><span data-stu-id="892fc-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
