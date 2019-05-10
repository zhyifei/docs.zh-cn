---
title: 演练：在 WPF 中承载 Direct3D9 内容
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: cff14f03a75717c657785cb8fe5a1de2077faf86
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605397"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="2bc18-102">演练：在 WPF 中承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="2bc18-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="2bc18-103">本演练演示如何承载 Windows Presentation Foundation (WPF) 应用程序中的 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="2bc18-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="2bc18-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2bc18-104">In this walkthrough, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="2bc18-105">创建用于承载 Direct3D9 内容的 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="2bc18-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
- <span data-ttu-id="2bc18-106">导入的 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="2bc18-106">Import the Direct3D9 content.</span></span>  
  
- <span data-ttu-id="2bc18-107">使用显示 Direct3D9 内容<xref:System.Windows.Interop.D3DImage>类。</span><span class="sxs-lookup"><span data-stu-id="2bc18-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="2bc18-108">完成后，您将知道如何进行承载 Direct3D9 内容在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc18-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2bc18-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="2bc18-109">Prerequisites</span></span>  
 <span data-ttu-id="2bc18-110">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="2bc18-110">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="2bc18-111">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2bc18-111">Visual Studio.</span></span>  
  
- <span data-ttu-id="2bc18-112">DirectX 9 或更高版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="2bc18-112">DirectX SDK 9 or later.</span></span>  
  
- <span data-ttu-id="2bc18-113">包含 WPF 兼容格式的 Direct3D9 内容的 DLL。</span><span class="sxs-lookup"><span data-stu-id="2bc18-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="2bc18-114">有关详细信息，请参阅[WPF 和 Direct3D9 互操作](wpf-and-direct3d9-interoperation.md)和[演练：创建在 WPF 中承载的 Direct3D9 内容](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc18-114">For more information, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="2bc18-115">创建 WPF 项目</span><span class="sxs-lookup"><span data-stu-id="2bc18-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="2bc18-116">第一步是创建 WPF 应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="2bc18-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="2bc18-117">创建 WPF 项目</span><span class="sxs-lookup"><span data-stu-id="2bc18-117">To create the WPF project</span></span>  
  
- <span data-ttu-id="2bc18-118">新的 WPF 应用程序项目中 Visual C# 创建名为`D3DHost`。</span><span class="sxs-lookup"><span data-stu-id="2bc18-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="2bc18-119">有关详细信息，请参见[演练：我第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc18-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
     <span data-ttu-id="2bc18-120">在中打开 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2bc18-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="2bc18-121">导入的 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="2bc18-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="2bc18-122">使用导入的 Direct3D9 内容从非托管 DLL`DllImport`属性。</span><span class="sxs-lookup"><span data-stu-id="2bc18-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="2bc18-123">要导入 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="2bc18-123">To import Direct3D9 content</span></span>  
  
1. <span data-ttu-id="2bc18-124">打开 MainWindow.xaml.cs 在代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="2bc18-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="2bc18-125">自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="2bc18-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="2bc18-126">承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="2bc18-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="2bc18-127">最后，使用<xref:System.Windows.Interop.D3DImage>类以承载 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="2bc18-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="2bc18-128">若要承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="2bc18-128">To host the Direct3D9 content</span></span>  
  
1. <span data-ttu-id="2bc18-129">在 MainWindow.xaml 中，自动生成的 XAML 将替换为以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="2bc18-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2. <span data-ttu-id="2bc18-130">生成项目。</span><span class="sxs-lookup"><span data-stu-id="2bc18-130">Build the project.</span></span>  
  
3. <span data-ttu-id="2bc18-131">将复制到 bin/Debug 文件夹的 Direct3D9 内容包含的 DLL。</span><span class="sxs-lookup"><span data-stu-id="2bc18-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4. <span data-ttu-id="2bc18-132">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="2bc18-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="2bc18-133">Direct3D9 内容出现在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc18-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc18-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bc18-134">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="2bc18-135">Direct3D9 和 WPF 互操作性的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="2bc18-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
