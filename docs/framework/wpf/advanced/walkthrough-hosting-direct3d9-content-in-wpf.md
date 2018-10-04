---
title: 演练：在 WPF 中承载 Direct3D9 内容
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 1fa4c2347448e23bbf740093541ec2b834df6705
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777508"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="4f55b-102">演练：在 WPF 中承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="4f55b-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="4f55b-103">本演练演示如何承载 Windows Presentation Foundation (WPF) 应用程序中的 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="4f55b-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="4f55b-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4f55b-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4f55b-105">创建用于承载 Direct3D9 内容的 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="4f55b-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="4f55b-106">导入的 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="4f55b-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="4f55b-107">使用显示 Direct3D9 内容<xref:System.Windows.Interop.D3DImage>类。</span><span class="sxs-lookup"><span data-stu-id="4f55b-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="4f55b-108">完成后，您将知道如何进行承载 Direct3D9 内容在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f55b-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4f55b-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="4f55b-109">Prerequisites</span></span>  
 <span data-ttu-id="4f55b-110">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="4f55b-110">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="4f55b-111">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4f55b-111">Visual Studio.</span></span>  
  
-   <span data-ttu-id="4f55b-112">DirectX 9 或更高版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="4f55b-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="4f55b-113">包含 WPF 兼容格式的 Direct3D9 内容的 DLL。</span><span class="sxs-lookup"><span data-stu-id="4f55b-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="4f55b-114">有关详细信息，请参阅[WPF 和 Direct3D9 互操作](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)并[演练： 创建内容为在 WPF 中承载的 Direct3D9](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="4f55b-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="4f55b-115">创建 WPF 项目</span><span class="sxs-lookup"><span data-stu-id="4f55b-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="4f55b-116">第一步是创建 WPF 应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="4f55b-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="4f55b-117">创建 WPF 项目</span><span class="sxs-lookup"><span data-stu-id="4f55b-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="4f55b-118">新的 WPF 应用程序项目中 Visual C# 创建名为`D3DHost`。</span><span class="sxs-lookup"><span data-stu-id="4f55b-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="4f55b-119">有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。</span><span class="sxs-lookup"><span data-stu-id="4f55b-119">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="4f55b-120">在中打开 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4f55b-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="4f55b-121">导入的 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="4f55b-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="4f55b-122">使用导入的 Direct3D9 内容从非托管 DLL`DllImport`属性。</span><span class="sxs-lookup"><span data-stu-id="4f55b-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="4f55b-123">要导入 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="4f55b-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="4f55b-124">打开 MainWindow.xaml.cs 在代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="4f55b-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="4f55b-125">自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="4f55b-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="4f55b-126">承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="4f55b-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="4f55b-127">最后，使用<xref:System.Windows.Interop.D3DImage>类以承载 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="4f55b-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="4f55b-128">若要承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="4f55b-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="4f55b-129">在 MainWindow.xaml 中，自动生成的 XAML 将替换为以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="4f55b-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="4f55b-130">生成项目。</span><span class="sxs-lookup"><span data-stu-id="4f55b-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="4f55b-131">将复制到 bin/Debug 文件夹的 Direct3D9 内容包含的 DLL。</span><span class="sxs-lookup"><span data-stu-id="4f55b-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="4f55b-132">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="4f55b-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="4f55b-133">Direct3D9 内容出现在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f55b-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f55b-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f55b-134">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="4f55b-135">Direct3D9 和 WPF 互操作性的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="4f55b-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
