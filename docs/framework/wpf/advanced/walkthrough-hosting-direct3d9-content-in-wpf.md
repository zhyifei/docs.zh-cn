---
title: "演练：在 WPF 中承载 Direct3D9 内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10558348a963f0b243dcfbe23171f6e24da6da0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="b9b3d-102">演练：在 WPF 中承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="b9b3d-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="b9b3d-103">本演练演示如何承载 Direct3D9 Windows Presentation Foundation (WPF) 应用程序中的内容。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="b9b3d-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b9b3d-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b9b3d-105">创建用于承载 Direct3D9 内容的 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="b9b3d-106">导入 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="b9b3d-107">通过使用显示 Direct3D9 内容<xref:System.Windows.Interop.D3DImage>类。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="b9b3d-108">当完成后时，你将知道如何承载 Direct3D9 内容在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9b3d-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="b9b3d-109">Prerequisites</span></span>  
 <span data-ttu-id="b9b3d-110">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="b9b3d-110">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="b9b3d-111">。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-111">.</span></span>  
  
-   <span data-ttu-id="b9b3d-112">DirectX 9 或更高版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="b9b3d-113">包含 Direct3D9 内容中的 WPF 兼容格式的 DLL。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="b9b3d-114">有关详细信息，请参阅[WPF 和 Direct3D9 间的互操作](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)和[演练： 创建内容的 WPF 中的托管的 Direct3D9](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="b9b3d-115">创建 WPF 项目</span><span class="sxs-lookup"><span data-stu-id="b9b3d-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="b9b3d-116">第一步是创建 WPF 应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="b9b3d-117">创建 WPF 项目</span><span class="sxs-lookup"><span data-stu-id="b9b3d-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="b9b3d-118">新的 WPF 应用程序项目中 Visual C# 创建名为`D3DHost`。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="b9b3d-119">有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-119">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="b9b3d-120">在中，打开 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="b9b3d-121">导入 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="b9b3d-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="b9b3d-122">使用导入 Direct3D9 内容从非托管 DLL`DllImport`属性。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="b9b3d-123">若要导入 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="b9b3d-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="b9b3d-124">在代码编辑器中打开 MainWindow.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="b9b3d-125">自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="b9b3d-126">承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="b9b3d-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="b9b3d-127">最后，使用<xref:System.Windows.Interop.D3DImage>类来承载 Direct3D9 的内容。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="b9b3d-128">要承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="b9b3d-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="b9b3d-129">在 MainWindow.xaml 中，替换下面的 XAML 自动生成的 XAML。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="b9b3d-130">生成项目。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="b9b3d-131">将复制包含 bin/Debug 文件夹将 Direct3D9 内容的 DLL。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="b9b3d-132">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="b9b3d-133">Direct3D9 内容出现在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9b3d-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b3d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9b3d-134">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="b9b3d-135">Direct3D9 和 WPF 互操作性的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="b9b3d-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
