---
title: 版本容错序列化技术示例
ms.date: 03/30/2017
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
ms.openlocfilehash: 34dccc9065c0100a01a7969a1fe762001e2999a9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210849"
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="3b03f-102">版本容错序列化技术示例</span><span class="sxs-lookup"><span data-stu-id="3b03f-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="3b03f-103">下载示例</span><span class="sxs-lookup"><span data-stu-id="3b03f-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="3b03f-104">此示例演示 .NET 序列化的版本容错功能。</span><span class="sxs-lookup"><span data-stu-id="3b03f-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="3b03f-105">此示例生成的应用程序使用不同版本的 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 对数据进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="3b03f-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="3b03f-106">尽管存在不同类型的版本，但应用程序仍可以进行无缝通信。</span><span class="sxs-lookup"><span data-stu-id="3b03f-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="3b03f-107">有关详细信息，请参阅[版本容错序列化](../../../docs/standard/serialization/version-tolerant-serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="3b03f-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="3b03f-108">使用命令提示生成示例</span><span class="sxs-lookup"><span data-stu-id="3b03f-108">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="3b03f-109">打开命令提示窗口，然后定位到该示例的语言特定子目录（在 V1 Application 或 V2 Application 之下）之一。</span><span class="sxs-lookup"><span data-stu-id="3b03f-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2.  <span data-ttu-id="3b03f-110">在命令行中键入“msbuild.exe \<ver> application.sln”（其中 \<ver> 为 v1 或 v2）。</span><span class="sxs-lookup"><span data-stu-id="3b03f-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="3b03f-111">使用 Visual Studio 生成示例</span><span class="sxs-lookup"><span data-stu-id="3b03f-111">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="3b03f-112">打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到该示例的特定语言的子目录。</span><span class="sxs-lookup"><span data-stu-id="3b03f-112">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="3b03f-113">定位到您在上一步中选择的目录的 V1 Application 子目录。</span><span class="sxs-lookup"><span data-stu-id="3b03f-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3.  <span data-ttu-id="3b03f-114">双击 V1 Application.sln 的图标，以便在 Visual Studio 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="3b03f-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4.  <span data-ttu-id="3b03f-115">在 **“生成”** 菜单上，单击 **“生成解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="3b03f-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="3b03f-116">定位到 V2 Application 子目录，重复前面两个步骤，以生成 V2 Application。</span><span class="sxs-lookup"><span data-stu-id="3b03f-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="3b03f-117">应用程序将在其各自项目目录的默认 \bin 或 \bin\Debug 子目录中生成。</span><span class="sxs-lookup"><span data-stu-id="3b03f-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="3b03f-118">运行示例</span><span class="sxs-lookup"><span data-stu-id="3b03f-118">To run the sample</span></span>  
  
1.  <span data-ttu-id="3b03f-119">在命令提示窗口中，定位到您在生成示例应用程序时选择的语言特定的子目录。</span><span class="sxs-lookup"><span data-stu-id="3b03f-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2.  <span data-ttu-id="3b03f-120">在命令行中键入“runme.cmd”，以同时运行这两个应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b03f-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="3b03f-121">或者，定位到包含新的可执行文件的目录，然后按顺序运行这些文件。</span><span class="sxs-lookup"><span data-stu-id="3b03f-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b03f-122">此示例生成控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b03f-122">The sample builds console applications.</span></span> <span data-ttu-id="3b03f-123">必须在命令提示窗口中启动并运行这些应用程序，才能查看相应的输出。</span><span class="sxs-lookup"><span data-stu-id="3b03f-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b03f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b03f-124">See also</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
- <xref:System.IO.FileStream>
